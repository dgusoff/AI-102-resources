# Secure Azure AI services

# authentication 

After completing this module, you will know how to:

Consider authentication for Azure AI services
Manage network security for Azure AI services

1. Key regeneration

use portal or: `az cognitiveservices account keys regenerate`

2. use key vault
can store subscription keys in key vault

3. token based auth
   use subscription key to obtain auth token which is good for ten minutes

4. entra id auth
a. create custom subdomain  `Set-AzContext -SubscriptionName <Your-Subscription-Name>`
b. create resource using subdomain: `$account = New-AzCognitiveServicesAccount -ResourceGroupName <your-resource-group-name> -name <your-account-name> -Type <your-account-type> -SkuName <your-sku-type> -Location <your-region> -CustomSubdomainName <your-unique-subdomain-name>`
c. register application and create principal and assign role

```
$SecureStringPassword = ConvertTo-SecureString -String <your-password> -AsPlainText -Force

$app = New-AzureADApplication -DisplayName <your-app-display-name> -IdentifierUris <your-app-uris> -PasswordCredentials $SecureStringPassword

New-AzADServicePrincipal -ApplicationId <app-id>

New-AzRoleAssignment -ObjectId <your-service-principal-object-id> -Scope <account-id> -RoleDefinitionName "Cognitive Services User"
```

5. auth using managed identity
system assigned or user assigned

ex
```
az vm identity assign -g <my-resource-group> -n <my-vm>
then grant via access control in portal
```

# network security

accessible by default to all networks, can secure in networking blade

## list keys

` az cognitiveservices account keys list --name <resourceName> --resource-group <resourceGroup>` 

test with curl

` curl -X POST "<yourEndpoint>/language/:analyze-text?api-version=2023-04-01" -H "Content-Type: application/json" -H "Ocp-Apim-Subscription-Key: <your-key>" --data-ascii "{'analysisInput':{'documents':[{'id':1,'text':'hello'}]}, 'kind': 'LanguageDetection'}"`

## use key vault

1. create a key vault
   Permission model: Vault access policy
   import key as secret

create svc principal
` az ad sp create-for-rbac -n "api://<spName>" --role owner --scopes subscriptions/<subscriptionId>/resourceGroups/<resourceGroup>`

Make a note of the appId, password, and tenant values

get object id: ` az ad sp show --id <appId> `

add permission
` az keyvault set-policy -n <keyVaultName> --object-id <objectId> --secret-permissions get list `

```
   // Get Azure AI services key from keyvault using the service principal credentials
                var keyVaultUri = new Uri($"https://{keyVaultName}.vault.azure.net/");
                ClientSecretCredential credential = new ClientSecretCredential(appTenant, appId, appPassword);
                var keyVaultClient = new SecretClient(keyVaultUri, credential);
                KeyVaultSecret secretKey = keyVaultClient.GetSecret("AI-Services-Key");
                aiSvcKey = secretKey.Value;

                // Get user input (until they enter "quit")
                string userText = "";
                while (userText.ToLower() != "quit")
                {
                    Console.WriteLine("\nEnter some text ('quit' to stop)");
                    userText = Console.ReadLine();
                    if (userText.ToLower() != "quit")
                    {
                        // Call function to detect language
                        string language = GetLanguage(userText);
                        Console.WriteLine("Language: " + language);
                    }

                }
```



