[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)]() <img src="https://img.shields.io/badge/platform-iOS-blue.svg?style=flat" alt="Platform iOS" /> <a href="https://developer.apple.com/swift"><img src="https://img.shields.io/badge/swift3-compatible-4BC51D.svg?style=flat" alt="Swift 3 compatible" /></a>

# Doodle Recognition

This very basic iOS app handles two things quite well:
  - Show you how drawing with the Apple Pencil works on a basic level
  - Show you how handwritten recognition works with Microsoft Cognitive Services

The first part is covered mainly in the MyDoodleCanvas.swift file, where the touch handling, drawing and triggering of the handwritten OCR is handled.
The second part is wrapped in the CognitiveServices.swift file, where two API calls are needed for getting the handwritten text within an image recognized. First you send the image to the textRecognition endpoint and get an operation_location URL back. Because the recognition can take a while, you are able to check back with this URL if the processing is already finished. If the status in the response is SUCCESS, the function just takes the result out of the text array and displays it right under your doodled text. 

<p align="center">
<img src="https://www.dropbox.com/s/oil95z0eak2wfj4/doodleRecognition.jpeg?dl=1" width="800">
</p>

If you need a more detailed explanation, just visit my medium posts on this topic. There are three of them and they cover the whole doodling and text recognition API calling super extensively but in a very easy way for you to comprehend.
  - [The Doodling Workshop #1 - Get a grip of your Apple Pencil](https://medium.com/@codeprincess/the-doodling-workshop-1-ae955e351f7b)
  - [The Doodling Workshop #2 - Recognise your handwriting](https://medium.com/@codeprincess/the-doodling-workshop-2-9c763c21c92b)

## Get yourself an API Key
Keep in mind to get yourself a Cognitive Services Computer Vision API Key to authenticate against the OCR API the app will use. But don’t worry. You’ll have one generated in no time and moreover get a free one for trial.

Just visit the [Getting Started page](https://azure.microsoft.com/en-us/try/cognitive-services/) and right after having your API key generated, add it at line 69 in the Cognitive Services.swift file or just add it plain in your own implementation when adding the Ocp-Apim-Subscription-Key field to your request header .
