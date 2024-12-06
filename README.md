
# Power Apps and Custom Vision Workshop
## Introduction
In this workshop, we will explore how to build powerful, AI-integrated applications using Power Apps and Azure Custom Vision. Azure Custom Vision is an image recognition service that allows you to train, deploy, and enhance your own image classification models for practical use in apps.


1. Download the dataset here - https://www.kaggle.com/datasets/mostafaabla/garbage-classification
2. extract zip file
3. follow step by step to create Project 

## Practical Exercises
### Practical 01: Image Analysis with Custom Vision
This exercise demonstrates how to use Azure Custom Vision for analyzing images, providing a foundational understanding of image classification.

### Practical 02: Object Detection with Custom Vision
Learn how to implement object detection in images using Azure Custom Vision. Detailed steps and code will be shared to help you create an object detection model.

### Practical 03: Integrating Custom Vision with Power Apps
Discover how to build an app in Power Apps that uses your trained Custom Vision model to classify images in real-time.




## 1. Create a Custom Vision Project in Azure
### Log in to Azure Portal
- Go to [Azure Portal](https://portal.azure.com/) and log in with your credentials.

### Create a Custom Vision Resource
1. Navigate to "Create a resource" > "AI + Machine Learning" > "Custom Vision".
2. Create a new Custom Vision resource, specifying the region, pricing tier, and other settings.
3. Once the resource is created, access it from the Azure portal.

### Set Up Your Custom Vision Project
1. Go to [Custom Vision](https://customvision.ai/) and log in using your Azure credentials.
2. Click "New Project", name your project (e.g., "Garbage Classification"), and select a domain (e.g., General).
3. Choose "Multiclass Classification" if you only need one label per image.

## 2. Upload and Tag Images for Training
### Upload Images
- Go to the "Images" tab in your Custom Vision project and upload the images you downloaded.

### Tag Images
- Assign tags (e.g., "Plastic", "Organic", "Paper") to each image to label them appropriately.

## 3. Train the Model
1. Click on **Train** and select **Quick Training** for faster results.
2. Review training metrics such as **Precision**, **Recall**, and **mAP** to evaluate the model's performance.

## 4. Publish the Model
1. Once training is complete, click on **Publish** and provide a name for the iteration.
2. Copy the **Prediction URL** and **API Key** from the **Prediction Resources** tab for later use.

## 5. Integrate the Model into Power Apps
### Create a Power Apps Canvas App
1. Log in to [Power Apps Studio](https://make.powerapps.com/).
2. Create a new **Canvas App** from scratch.

### Add and Configure Controls
1. Add an **Upload Image** control to allow users to upload images.
2. Add a **Button** to trigger the classification process.
3. Add a **Gallery** control to display the results.

### Connect to the Custom Vision API
1. Go to **Data** > **+ Add data** > **Custom Connector**.
2. Create a new Custom Connector using the **Prediction URL** and **API Key**.

### Write the Formula to Classify Images
Use the following formula to send the image to the Custom Vision API:
```PowerApps
ClearCollect(
  Predictions,
  GarbageClassifier.PredictImage({
    image: UploadedImage.Image
  })
)
```
- Replace `GarbageClassifier.PredictImage` with the method you created in the Custom Connector.

### Display Results
1. Set the `Items` property of the Gallery to `Predictions`.
2. Configure the gallery to display the label and confidence score of each prediction.

## 9. Test and Evaluate the App
- Upload test images and click the button to see the classification results.
- Ensure the app correctly displays the label and confidence score for each image.
- Adjust training and retrain if the accuracy is not satisfactory.






## Documentation
- [Microsoft Azure AI Fundamentals: Computer Vision](https://learn.microsoft.com/en-us/training/paths/explore-computer-vision-microsoft-azure/)
- [Image classification with custom Azure AI Vision models](https://learn.microsoft.com/en-us/training/modules/custom-model-ai-vision-image-classification/)

## Feedback
If you have any feedback or questions, please feel free to reach out to me:

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ayodhya-j-weerabahu/)
