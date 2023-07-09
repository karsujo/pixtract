# PIXTRACT
A searchable image storage database.
# Introduction
A cloud-first serverless application to leverage state of the art machine learning and image processing algorithms to create a cloud-native, media storage and search application, entirely built using a serverless architecture. This application will enable images to be stored on the cloud, as Ill as perform automatic image tagging, recognition, categorization and digital notes extraction to enable a global search interface where every media content uploaded is text-searchable. 

# Features

![Main Img](./Readme/assets/images/image18.png)

## **Authentication and Image storage**
 Store images on the cloud (Image upload/download). Users can use this as a personal cloud gallery, similar to google photos. 
## **Auto Categorization** 
 Automatically categorise images into groups (folders), and suggest category names. Use Image processing algorithms (via AWS Rekognition) to detect object and assign lables. 
## **Image Tagging & Metadata** 
 Leverage Image processing to extract information from images such as objects, scenes, locations, scenes and contexts. Group lables to form categories. 
## **Notes Digitization** 
 Use OCR and image-text conversion to extract textual info from images such as class notes, bill receipts, filled forms etc. This is enabled via AWS Textract. 
## **Global Search** 
 Search images across digitized notes and normal pictures based on key text inputs using free-form text search (Lucene).

# AWS Cloud Architecture
![Main Img](./Readme/assets/images/image2.png)
A brief overview of the different AWS services and how they are integrated into this application:
## Amplify
 I have used Amplify to streamline the development process and simplify the integration of various AWS services into our application.One of the key benefits of Amplify is its ability to automate the deployment and configuration of cloud infrastructure for our application.
## API Gateway
Using API Gateway, I have created several APIs that enable our frontend to communicate with other services, such as Lambda functions and DynamoDB databases. This enables us to perform a range of functions, such as user authentication, data retrieval, and data storage, all of which are essential for a cloud-native, serverless application like Pixtract.
## Cognito
 Using Cognito, I have created APIs for user signup and signin, allowing users to authenticate themselves using a username and password.When a user signs up or signs in to our application, Cognito returns a user token, which I use to authenticate the user and authorize them to perform certain actions within our application. 
## Dynamo
I use DynamoDB to store metadata related to uploaded images. Specifically, I use DynamoDB to store the metadata associated with each image uploaded to our application.When a user uploads an image to Pixtract, I store the image file itself in an Amazon S3 bucket, and then extract its metadata using AWS Rekognition and Textract. 
## S3
 S3 is a highly scalable, durable, and secure object storage service that provides us with a reliable and cost-effective solution for storing and serving static content, such as images and video files. When a user uploads an image to Pixtract, I store the image file in an S3 bucket. In addition to uploading images, our users can also download their images from S3
## Lambda
Lambda is a serverless computer service that enables us to run code without provisioning or managing servers. I use Lambda to execute serverless functions that perform automated image tagging and recognition, enabling us to easily categorize and label images for easy search and retrieval.
## Textract 
Amazon Textract is a machine learning (ML) service that automatically extracts text, handwriting, and data from scanned documents. It goes beyond simple optical character recognition (OCR) to identify, understand, and extract data from forms and tables
## Rekognition
Amazon Rekognition is based on the same proven, highly scalable, deep learning technology to analyze billions of images and videos daily. Amazon Rekognition includes a simple, easy-to-use API that can quickly analyze any image or video file that’s stored in Amazon S3
## Open search
Amazon OpenSearch is a search and analytics engine that I have used in our Pixtract Ib application to provide advanced search functionality for our users. With OpenSearch, I are able to perform complex search queries on the metadata associated with each image uploaded to our application. 
# Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

## Folder Structure 

All the .py files in the /lambda folder under src are the code for the lambda functions that Ire used to communicate with various AWS services. 
The tests folder has the postman test collecton for all the API endpoints. 

***

This was developed as a part of the CS552 Cloud Computing Course. A full, detailed report of the project can be found here. [Report.pdf](Report.pdf)


