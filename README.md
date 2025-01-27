☁️ Image labels generator using Amazon Rekognition ☁️ 

☁️ Overview of Project ☁️

In this project, we will be building an image labels generator, using Amazon Rekognition. Once built, it will be able to recognize and label images. For example, if you have a photo of a cat, Amazon Recognition will be able to identify what it is, and label the image as a cat.
Steps to be performed 

Steps.

    Creating an Amazon S3 Bucket
    Uploading images to the S3 Bucket
    Installing configuring the AWS Command line interface (CLI)
    Importing libraries
    Adding detect_labels function
    Adding main function
    Running  python file


🛠 Services Used 🛠

    Amazon S3: For storing the images in the process of generating labels.
    Amazon Rekognition: To analyse images and generate image labels.
    AWS CLI: Interacting with AWS services through command line interface(CLI).

Architectural Diagram

This it the architectural diagram for the project:

![AWS Cloud](https://github.com/user-attachments/assets/e5ed9f35-c28c-419e-a933-75e224922126)

Create an Amazon S3 Bucket

Log in to your AWS Management Console.
Go to Amazon S3 from the search bar. An S3 bucket is like a virtual storage box in the cloud where me can store my files securely and with easy-to-access permissions.

![1A](https://github.com/user-attachments/assets/75dc4005-4eb5-46f6-be8a-6958be353997)

Click on ‘Create Bucket’.

![01](https://github.com/user-attachments/assets/2f9fcd4a-ea6a-474f-9736-219c3a072370)

Upload Images to S3 Bucket


![02](https://github.com/user-attachments/assets/f4ed949a-3a12-4c2f-a37d-387fbfc27869)

Click on Upload. Your image has now been uploaded in the S3 bucket.


![03](https://github.com/user-attachments/assets/c0c9db78-e554-4662-bbde-d49364aa82eb)

Installing the AWS Command line interface(CLI)


![33](https://github.com/user-attachments/assets/399e955e-bcb7-4c6a-ac47-f1bf8e6fcb6d)

Configure AWS CLI

    To configure your AWS CLI, run the following command in your terminal:

    aws configure

    Running this command will ask for a access key and secret access key.
    What are these?
    To access your AWS account from CLI, you need to set up a user account associated with it and these keys are used for the authentication for accessing the AWS services.

    Login to your AWS Management console and search for IAM in the search bar.

    Navigate to Users and click on Create User.

    Give an appropriate user name and click Next.

    
![8](https://github.com/user-attachments/assets/71b1d7fb-ede5-4084-a113-d41774979a12)

Attach policies directly


![9](https://github.com/user-attachments/assets/6abd61b0-77f3-4aa7-b979-72d26a416386)


![15](https://github.com/user-attachments/assets/b5207e65-1773-4c45-82e6-2082e704d5fc)

The general flow of the command line would look like:

Importing Libraries

    Open preferred IDE(VSCode etc.) to and create a .py file for performing your coding.
    Open a terminal and install the libraries needed for this project.

    pip install boto3
    pip install matplotlib

    Let's import the necessary libraries. We need:

        boto3 for interacting with AWS services.
        matplotlib for visualization.
        PIL (Python Imaging Library) for handling image data.
        BytesIO from the io module to work with image data.

    Add the below code in your .py file.

    
![py01](https://github.com/user-attachments/assets/42c133b8-6b41-4c1b-a310-33c002e8f16a)

Define Functions

detect_labels function

Now, let's define a function called detect_labels. This function takes a photo and bucket name as input parameters. Within the function:

    We create a Rekognition client using boto3.
    We use the detect_labels method of the Rekognition client to detect labels in the given photo.
    We print the detected labels along with their confidence levels.
    We load the image from the S3 bucket using boto3 and PIL.
    We use matplotlib to display the image and draw bounding boxes around the detected objects.

![21](https://github.com/user-attachments/assets/b8181dc6-0c9a-4f10-b177-c63beb6967b4)

main function

Next, let's write a main function to test our detect_labels function. We specify a sample photo and bucket name, then call the detect_labels function with these parameters.


![py02](https://github.com/user-attachments/assets/77c16b85-d303-43b6-8bfb-a0706e29b45d)

Running Python file

    Open the terminal in the directory where your Python file is present and run the command:

    python name_of_python_file.py

    You will get an output with 10 detected labels and their confidence levels and a pop-up screen displaying the image that was uploaded on your S3 bucket with the bounding boxes present on the generated labels. 

  

![3A](https://github.com/user-attachments/assets/78a7b6e9-beb9-43b5-b576-76a131a5833d)

