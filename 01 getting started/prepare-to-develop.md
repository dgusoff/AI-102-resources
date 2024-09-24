1 Prepare to develop AI solutions on Azure

https://learn.microsoft.com/en-us/training/modules/prepare-to-develop-ai-solutions-azure/




Define Artificial Intelligence
* Visual Perception - accept, interpret, process input form images, video streams, cameras
* text Analysis and Conversation - use NLP to read and generate realistic responses and extract semantic meaning from text
* Speech - recognize as input and synthesize as output - conversational AI
* Decision Making - past experience, learned correlaitons -> assess and act


## AI Terms

Data Science
* processing and analysis
* apply statistical techniques
* extrapolate - understand trands and relaitonships

Machine Learning
* training and validation of predictive models
* exploit *features* in data to predict values for unknown *labels*

Artificial Intelligence
* software that emulates one or more charatceristics oh human intelligence
* use machine learnng to create AI software




# understand considerations for AI Engineers


## model training and inferencing
1. training process determines relaitonships between features in data and labels - the value trying to be predicted
2. Probability and confidence scores - predictions will have a confidence score
3. responsible AI and ethics
  * predictions depend on quality of data input
  * can lead users to trust
  * potential for harm through inaccuracy or misuse

  # COnsiderations for Responsible AI

  ## Fairness
  * consider form the beginning of process

  ## reliability and safety
  * consider: autonomous vegicle; medical diagnosis
  * rigorous testing and deployment management processes
  * apply appropriate probability thresholds

  ## Privacy and security
  * learning model data might be sensitive
  * safeguards to protect data and customer content

## inclusivenenss
* include input form diverse sources

## transparency
* purpose and function of system should be understandable
* users hsould know how data is being used

## accountability
* responsibility of developers who ttrained/validated model and decision model
* shoudl work within a governance framework

# Capabilities of Azure machine learning

1. automated machine learning - enable no experts to create effective model from data
2. Azure ML designer - graphical no-code interface
3. Data and compute management - cloud based data storage and compute resources
4. pipelines - orchestrate model traiining, deployment, and mgmt tasks

can use to:
1. ingest and prep data
2. run experiments to explore and train
3. deploy trained models as web services

# capabilities of Azure AI Services

## categories

## NLP
* text analysis
* Question answering
* language understanding
* Translation
* named entity recognition
* custom text classification
* Speech
* Sppech translation

## Knowledge mining and document intelligence
* AI search
* Document intelligence
* Custom document intelligence
* Custom skills

## computer vision
* Image analysis
* Video Analysis
* image classification
* Object detection
* Facial Analysis
* optical character recognition
* azure AI video indexer

## decision support
* content safety
* content moderation

## generative AI
* Azure OpenAI service
* DALL_E image generation

# Capabilities of Azure OpenAI Service
* AI models that generate content
* text, images, code, more
* depend on Large Language Models- queried with natural language prompts
* exposes Models developed by OpenAI
* REST and language specific SDKs

documentation: https://learn.microsoft.com/en-us/azure/ai-services/openai/


# capabilities of Azure AI Search
* ingest an dindex form various sources
* searc index to find, filter, sort extracted data
* enrichment pipeline - enhance with insights derived from source data
* ex, generate descriptions of images, determine key phrases
* insights can be persisted in knowledge store



