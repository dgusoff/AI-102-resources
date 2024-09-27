# Access Azure OpenAI Service

## create the resource

-- name must be unique per region

![alt text](image.png)

![alt text](image-1.png)

![alt text](image-2.png)

## Create in CLI

```
az cognitiveservices account create \
-n MyOpenAIResource \
-g OAIResourceGroup \
-l eastus \
--kind OpenAI \
--sku s0 \
--subscription subscriptionID
```

certain models might not be available in certain regions