# content safety

drivers:
Increase in harmful content: There's been a huge growth in user-generated online content, including harmful and inappropriate content.
Regulatory pressures: Government pressure to regulate online content.
Transparency: Users need transparency in content moderation standards and enforcement.
Complex content: Advances in technology are making it easier for users to post multimodal content and videos.


Note: Azure AI Content Safety replaces Azure Content Moderator, which was deprecated in February 2024 and will be retired by February 2027.

part of Azure Ai FOundry

Azure AI Content Safety works with text and images, and AI-generated content.

four categories: Hate, Sexual, Self-harm, violence

**Text content**
scan across the 4 categories, severity level 0 to 6 is issued

propmpt shield - identify and block jailbreak attempts. user inout and documents

protected material detection - copyrighted stuff

groundedness - protect against innaccurate reponses in LLM text
adds a reasoning field to response. increases processing and cost

**image content**
moderate - scans across four categories
moderate multimodal content - scans both images and text, suck as OCR data

**custom solutions**
provide custom categories and add positive and negative examples
can customize safety system message

**limitations**
stuff can slip through
always test on real data 


evaluate accuracy
True positive - correct identification of harmful content.
False positive - incorrect identification of harmful content.
True negative - correct identification of harmless content.
False negative - harmful content isn't identified.

**When to use Azure AI Content Safety**
education
social
brands
e commerce
gaming
generative ai solution
news
others, cn be customized

exercize https://microsoftlearning.github.io/mslearn-ai-services/Instructions/Exercises/05-implement-content-safety.html

create resource



