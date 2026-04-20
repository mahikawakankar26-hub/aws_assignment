#  AWS Static Website Hosting Project

##  Project Overview
This project demonstrates how to build and deploy a static website using Amazon Web Services (AWS). The website consists of three pages—Home, About, and Contact—and is hosted using Amazon S3 with secure and minimal access configurations.

---

##  Objective
To create a low-cost, scalable, and publicly accessible static website while implementing secure deployment practices using AWS services like S3 and IAM.

---

##  Technologies Used
- HTML5  
- CSS3  
- AWS S3 (Static Website Hosting)  
- AWS IAM (Access Control)  

---

##  What is AWS?
Amazon Web Services (AWS) is a cloud computing platform that provides services such as storage, computing, networking, and security. It allows users to build scalable and cost-effective applications without managing physical infrastructure.

---

##  AWS Services Used

### 1. Amazon S3 (Simple Storage Service)
- Used to store and host static website files  
- Provides high availability and durability  
- Supports static website hosting  
- Cost-effective and easy to configure  

### 2. AWS IAM (Identity and Access Management)
- Used to control access to AWS resources  
- Implements least privilege principle  
- Created a user with limited permissions for S3 operations  

---

##  Project Structure
 - aws-assignment
   - index.html
   - about.html
   - contact.html
   - style.css
---

##  Step-by-Step Deployment Guide

###  Step 1: Create Website Files
1. Open Visual Studio Code  
2. Create:
   - index.html  
   - about.html  
   - contact.html  
   - style.css  
3. Add HTML and CSS code  
4. Test in browser  

---

###  Step 2: Push Code to GitHub
`bash
git add .
git commit -m "Initial project setup"
git push `


###  Step 3: Create S3 Bucket
1. Go to AWS Console  
2. Search for **S3**  
3. Click **Create Bucket**  
4. Enter a unique bucket name  
5. Select region  
6. Uncheck **Block all public access**  
7. Acknowledge the warning  
8. Click **Create Bucket**  

---

###  Step 4: Upload Website Files
1. Open the created bucket  
2. Click **Upload**  
3. Click **Add files**  
4. Select:
   - index.html  
   - about.html  
   - contact.html  
   - style.css  
5. Click **Upload**  



###  Step 5: Enable Static Website Hosting
1. Go to **Properties tab**  
2. Scroll to **Static Website Hosting**  
3. Click **Edit**  
4. Enable hosting  
5. Enter:
   - Index document: `index.html`  
6. Click **Save changes**  

---

###  Step 6: Configure Bucket Policy
1. Go to **Permissions tab**  
2. Scroll to **Bucket Policy**  
3. Click **Edit**  
4. Paste the following:

`json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}`
###  Step 7: Access the Website
1. Go to your S3 bucket  
2. Click on the **Properties tab**  
3. Scroll down to **Static Website Hosting**  
4. Copy the **Endpoint URL**  
5. Paste the URL into your browser  
6. Verify that:
   - Home page loads correctly  
   - Navigation to About and Contact pages works  


###  Step 8: Create IAM Policy
1. Go to AWS Console  
2. Search for **IAM**  
3. Click on **Policies → Create Policy**  
4. Select the **JSON** tab  
5. Paste the policy

