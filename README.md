# AWS-Cloud-Static-Udacity
🌐 Deploy Static Website on AWS 🧠 Project Overview

This project demonstrates how to deploy a static website on AWS using the following key services:

Amazon S3 – to host the website files

Amazon CloudFront – to distribute content globally with low latency

AWS IAM – to manage access and permissions securely

📂 Project Structure
/
├── index.html          # The primary HTML file (homepage)
├── /img                # Directory containing background and image assets
├── /vendor             # Bootstrap, Font Awesome, and JavaScript library dependencies
├── /css                # Custom CSS stylesheets for the website
└── README.txt          # Project description and setup instructions
└── /Screenshots        # Project screenshots

🚀 Deployment Steps

1.Create an S3 Bucket

.Open the AWS S3 Console

.Click Create bucket and enter a unique bucket name (e.g., lavanya192003)

<img width="1920" height="981" alt="S3 Bucket Files" src="https://github.com/user-attachments/assets/8f8349f5-4635-4b61-9fb3-e9eb19ab3ba5" />

.Uncheck Block all public access 

<img width="1920" height="976" alt="S3 Block Public Access" src="https://github.com/user-attachments/assets/267052ae-2039-4968-9fe2-34972ba6e266" />

.Enable Static website hosting under Properties

<img width="1920" height="974" alt="S3 Enable Static Website hosting" src="https://github.com/user-attachments/assets/35c69ee8-265c-4ea2-a044-d53a2350d7e1" />

.Set the index document to index.html image Bucket Configuration
<img width="1920" height="975" alt="S3 endpoint URL" src="https://github.com/user-attachments/assets/6d284a89-3a9b-44b4-904c-88f941015baa" />


2.Upload Website Files

.Upload all files and folders:

.index.html

./img

./vendor

./css

Then make the files publicly readable (via permissions or bucket policy).

<img width="1920" height="977" alt="S3 Uploaded Files" src="https://github.com/user-attachments/assets/7bbc519f-80ac-449b-b15e-9e428ea11fd9" />

3.Set Bucket Policy
Add the following bucket policy to allow public read access:

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```
<img width="1920" height="984" alt="S3 Bucket Policy" src="https://github.com/user-attachments/assets/1500cb0e-7465-4721-b7b2-74fffd262638" />

4.Configure CloudFront
.Go to CloudFront Console → Create Distribution

<img width="1920" height="964" alt="CloudFront Distributions" src="https://github.com/user-attachments/assets/16fb2719-4f4c-4c9e-ba4a-bf99e11ad24f" />

.Go to origin → Choose your S3 bucket 

<img width="1920" height="971" alt="CloudFront Origin" src="https://github.com/user-attachments/assets/42ec1af3-5ee8-4a74-af33-dbd4d8a7808c" />
<img width="1920" height="968" alt="CloudFront EnableOrign" src="https://github.com/user-attachments/assets/6685d4b6-3914-4cf5-a39c-1d195c30a21b" />

Go to Behaviors → Enable Redirect HTTP to HTTPS for security 

<img width="1920" height="971" alt="CloudFront Behavior1" src="https://github.com/user-attachments/assets/789eb67e-3744-4db4-8e5b-6235599b1b2a" />
<img width="1920" height="971" alt="CloudFront Behavior2" src="https://github.com/user-attachments/assets/fd53bdb3-1668-4f50-8f32-00946f029dec" />

Deploy — you’ll get a CloudFront URL to access your site globally

<img width="1920" height="974" alt="CloudFront deploy" src="https://github.com/user-attachments/assets/8b23c21b-e4f1-436f-bdf9-a6583c96814b" />

Verify Your Website

Open your CloudFront URL or S3 website endpoint in a browser.Your static website should now be live.

Live S3 Website URL: http://lavanya192003.s3-website-us-east-1.amazonaws.com/

<img width="1920" height="977" alt="Live S3 Website" src="https://github.com/user-attachments/assets/9a47ca25-47b4-4dbf-ab1d-c68751436de4" />

Live CloudFront URL: https://dkyeacrb1hjnq.cloudfront.net/

<img width="1920" height="1020" alt="CloudFront Website" src="https://github.com/user-attachments/assets/4d2b05ca-7629-48c6-a102-5b3a4d777842" />

Once you launch your website URL will look like this and terminating your bucket and CloudFront the URL will not work.!

👩‍💻 Technologies Used

HTML5

CSS3

Bootstrap (via /vendor/)

Font Awesome

Amazon S3

Amazon CloudFront

AWS IAM
AWS IAM
🏁 Expected Outcome

By completing this project, you will:

Understand AWS S3 static website hosting

Learn how to configure CloudFront for global distribution

Manage IAM permissions and bucket policies securely

Successfully deploy and host a professional static website

You can unzip the udacity folder for vendor folder.
