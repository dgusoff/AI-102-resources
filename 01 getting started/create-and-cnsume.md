# Create and consume Azure AI services

Multi-service vs single service

endpoint and keys
endpoint uri
subscription key
resource location

rest api

sdk

lab https://microsoftlearning.github.io/mslearn-ai-services/Instructions/Exercises/01-use-azure-ai-services.html

```
 static string GetLanguage(string text)
        {

            // Create client using endpoint and key
            AzureKeyCredential credentials = new AzureKeyCredential(AISvcKey);
            Uri endpoint = new Uri(AISvcEndpoint);
            var client = new TextAnalyticsClient(endpoint, credentials);

            // Call the service to get the detected language
            DetectedLanguage detectedLanguage = client.DetectLanguage(text);
            Console.WriteLine("detectedLanguage: " + detectedLanguage);    
            return(detectedLanguage.Name);

        }
```


