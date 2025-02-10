# Create an Amazon S3 Bucket 
#### [Made by Tasha Penwell with Scribe](https://scribehow.com/shared/Create_an_Amazon_S3_Bucket__b-l-u_DgTQCxfPHVWi9WhA)
This guide offers a comprehensive overview of how to create and manage an Amazon S3 bucket, highlighting its powerful features like scalability, durability, and security. It provides step-by-step instructions on setting up a bucket, configuring access controls, and utilizing advanced functionalities such as versioning, lifecycle rules, and replication, making it an invaluable resource for anyone looking to effectively leverage S3 for data storage and management.

Amazon S3 (Simple Storage Service) is a scalable, high-speed, web-based cloud storage service designed for online backup and archiving of data and application programs.

**Core Functionality of S3**

- Object storage service that offers industry-leading scalability, data availability, security, and performance
- Stores data as objects within buckets, with each object consisting of a file and optional metadata
- Provides 99.999999999% (11 9's) of durability
- Provides 99.99% of availability of objects over a given year

**Key Features**

- **Scalability**: Virtually unlimited storage capacity
- **Durability**: Designed to provide 99.999999999% durability of objects
- **Availability**: Offers 99.99% availability
- **Security**: Supports encryption at rest and in transit
- **Versioning**: Keeps multiple versions of an object in the same bucket
- **Access Control**: Uses bucket policies and Access Control Lists (ACLs)
- **Storage Classes**: Offers various storage tiers for different use cases

**Use Cases**

- Backup and storage
- Application hosting
- Media hosting
- Software delivery
- Data lakes and big data analytics
- Static website hosting
- Disaster recovery


## Task 1 - Go to [aws.amazon.com](http://aws.amazon.com) and sign in. In the search field, type *S3* and select it from the display.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-08/cd47c6ba-ba79-47c6-9d2e-83e31b41b467/user_cropped_screenshot.jpeg?tl_px=0,0&br_px=2994,1640&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=286,84)


## Task 2 -  Creating a Bucket


In the S3 console, select **Create bucket**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/4e05ec7e-6138-4967-bc75-68fab7ff3d4d/ascreenshot.jpeg?tl_px=272,140&br_px=3024,1679&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=992,277)


**2.1.** Under **General Configuration** you can choose between *General purpose* and *Directory*.

The General purpose one is used in most cases and is what this demo is using.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/21bf48f5-4e96-4d26-847c-4d627551bbec/ascreenshot.jpeg?tl_px=0,218&br_px=2752,1757&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=485,277)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**2.2.** There are two bucket types. The General purpose one is used in most cases. Review the information below for more details on the difference between these two types of buckets.

- **General purpose buckets**

  - The original S3 bucket type
  - Recommended for most use cases and access patterns
  - Allow objects that are stored across all storage classes

- **Directory buckets**

  - Support bucket creation in an Availability Zone or Local Zone.
  - Directory buckets in Availability Zones support the S3 Express One Zone storage class.
    - S3 Express One Zone storage class is recommended if your application is performance sensitive and *benefits from single-digit millisecond* `PUT` *and* `GET` *latencies.*
    - For *data residency use cases*, you can create a directory bucket in a single AWS Dedicated Local Zone (DLZ) to store data.
    - Directory buckets in Local Zones support the S3 One Zone-Infrequent Access (S3 One Zone-IA; Z-IA) storage class.
  - Directory buckets in Local Zones support the S3 One Zone-Infrequent Access (S3 One Zone-IA; Z-IA) storage class.
  - Directory buckets organize data hierarchically into directories as opposed to the flat storage structure of general purpose buckets.
---
<br>

**2.3.** Enter a globally unique bucket name.  Bucket names must meet naming requirements and must be unique from any other bucket name in any other AWS account.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7d9350f0-e589-499c-947a-9ae2f6e003ae/ascreenshot.jpeg?tl_px=0,306&br_px=2752,1845&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=462,276)

<img src="https://github.com/user-attachments/assets/b10c7044-6d7e-4fc7-a3c2-6b30d55647b8" alt="Tip icon" width="50" height="50" style="vertical-align: middle;">

Tip: - Bucket names **must** be unique across all AWS accounts in all the AWS Regions within a partition.

- A bucket name can't be used by another AWS account until the bucket is deleted.
---
<br>

**2.4.** Select **Object Ownership** between *ACLs disabled* and *ACLs enabled.*

Access Control Lists (ACLs) enable you to manage access to buckets and the objects in it.

It is recommended that ACLs are disabled and use bucket and/or IAM policies to control access to the objects in the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7d0ae9fa-ca79-4335-abbd-3aaaae10bd41/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=377,321)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">


**2.5.** Each bucket and object has an ACL attached to it and defines AWS accounts or groups that are granted access and what type of access.

When a request is received, S3 checks the attached ACL to verify if the requester has the correct access permissions.

**S3 Object Ownership** is a bucket level setting that can be used to control ownership of the bucket and the objects in it.

*ACLs disabled* is used so the bucket owner owns all the objects and manages access to them exclusively.

*ACLs enabled* is used in unusual circumstances where each object needs individual control access instead of the bucket owner. 

---
<br>

**2.6.** Adjust settings as needed to **Block Public Access settings for this bucket**.

These options provide settings for access points, buckets, and accounts to help you manage public access to Amazon S3 resources.

Allows you to set up centralized controls to limit public access to resources that are enforced regardless of how the resources are created.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/407a2001-7e05-4d91-8157-f3af0926f27b/ascreenshot.jpeg?tl_px=0,179&br_px=2752,1718&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=246,277)
---
<br>

**2.7.** Decide if you want to enable **Bucket Versioning**

Versioning is used to keep multiple versions of an object.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/dcb7c6bd-fa93-43d5-9e2d-e9c5fa1cee10/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=133,401)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">
---

**2.8.** Benefits of using versioning

- can restore objects if they are accidentally overwritten
- can restore objects if they are accidentally deleted

How Versioning Works

- If an object is overwritten, S3 adds a new object version in the bucket. The previous version remains in the bucket and becomes a noncurrent version. This noncurrent can be restored if needed.
- If an object is deleted, the object is not removed permanently. Instead, S3 inserts a delete marker. This object becomes the current object version. The previous version can be restored (if one exists).

It is important to know that once versioning is enabled, it cannot be disabled.

Learn more about Amazon S3 version control at <https://docs.aws.amazon.com/AmazonS3/latest/userguide/versioning-workflows.html>

<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">
---

**2.9.** Remember that billing in S3 is a pay-as-you-go service and charges are based on the objects stored. The rate depends on the size of the object, how long it is stored, and the storage class. The rates apply to every version of an object that is stored. ***Each version of an object is the entire object.***

Once versioning is enabled, it cannot be disabled but can be suspended to stop creating versions as objects are overwritten or deleted.

---
<br>

**2.10.** **Tags** can be added. A tag is a label consisting of a key and (optional) value to store additional data (metadata) about the resource.

Tags can be used to filter and search for resources, monitor cost and usage, and manage the AWS environment.

Tags are not required but is a best practice as part of building a Well-Architected Framework in AWS. Tags can be added when a resource is created or after it is launched.  We will not be adding tags in this demo.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/4afa56fe-9e5d-491b-9ab7-e842a8a30645/ascreenshot.jpeg?tl_px=0,136&br_px=2752,1675&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=140,277)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">


**2.11.** Tags can be added to new objects as they are uploaded or can be added to existing objects as needed.

Some basic rules regarding tags

- You can add up to 10 tags to an object.
- Tags associated with an object must have unique tag keys
- Tags are case-sensitive. White space also counts as a character

Learn more at <https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-tagging.html>

---
<br>

**2.12.** Encryption is a best practice and is automatically applied to S3 buckets. You can customize the **Default encryption** to one of three different types.

- *Server-side encryption (SSE) with Amazon S3 managed keys. This is known as SS3-S3*
- *Server-side encryption (SSE) with Amazon Key Management Service (KMS). This is known as SS3-KMS.*
- *Dual-layer server-side encryption with AWS Key Management Service keys (DSSE-KMS)*

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/a054a873-df20-4d82-9549-d2aeba68df1f/ascreenshot.jpeg?tl_px=0,85&br_px=2752,1624&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=460,277)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**2.13.** In January 2023, Amazon began encrypting S3 buckets by default. New objects are automatically encrypted by using server-side encryption with Amazon S3 managed keys (SSE-S3) and are at no cost.

If an organization needs more control over encryption keys such as managing key rotation and access policy grants (due to organizational requirements, compliance, etc.), the following presents additional choices.

- Server-side encryption with AWS Key Management Service keys (SSE-KMS)
- Dual-layer server-side encryption with AWS Key Management Service keys (DSSE-KMS)

Server-side encryption with customer-provided keys (SSE-C) is not supported for default encryption.

---
<br>

+ Tip
**2.14.** Objects uploaded before default encryption was enabled (January 2023) will not be encrypted.
 
 
<br>

**2.15.** Make a selection on the **Bucket Key** to enable or disable.

When using SSE-KMS, you can add an S3 Bucket key. Bucket keys can decrease the costs for S3 requests to KMS which can reduce the cost of SS3-KMS.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/d273f17a-82b9-4c25-a261-ce38c092a980/File.jpeg?tl_px=0,85&br_px=2752,1624&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=460,277)

---
<br>

**2.16.** Click **Create bucket** to create the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e207dab5-09f5-4109-b461-f34c0383cb0e/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=991,519)

---
<br>

**2.17.** If your bucket was created successfully, a green batter will appear at the top of the screen. 

If the bucket was not successfully created, a red banner will appear instead. This red banner will provide a message to help troubleshoot.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/752a2441-98ba-49d5-bc0d-b85f16a62eef/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=991,178)


### Reviewing the Bucket


 With the newly created bucket, we see there are tabs and other options to use this storage service.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/8ca23fce-9f66-41b1-b61d-6ce6b129f695/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=264,189)

--- 

## Task 3 -  Adding Objects to the Bucket

<br>

**3.1.** Objects in a bucket can be thought of similarly as files you add to your local file folder or upload to other platforms such as Google Drive. The bucket-object relationship is similar to the folder-file relationship.

<br>

**3.2.** To upload files into the bucket, verify you are in the **Objects** tab is selected and click **Upload**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/3ab9590a-bc2a-4e3d-9868-db01d2a31c82/ascreenshot.jpeg?tl_px=184,351&br_px=2936,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,335)

---
<br>

**3.3.** Click **Add files** to find the files (objects) to upload into the bucket. You will see a window (File Explorer, Finder, etc.) to select the files to upload.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/38359f2e-87d9-4075-bf49-809f311a5a96/ascreenshot.jpeg?tl_px=272,117&br_px=3024,1656&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=878,277)

---
<br>

**3.4.** Files are added

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/3f841379-52b0-4573-9cec-1871ced47310/ascreenshot.jpeg?tl_px=0,145&br_px=2752,1684&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=464,276)

---
<br>

**3.5.** Optionally, you can adjust the *Permissions* and *Properties* for the uploaded objects.

*Permissions* are dependent upon the bucket settings. For example, if the bucket is bucket owner enforced for Object Ownership, the bucket policies would need to be updated. Recall that Access Control Lists (ACLs) are used to help determine ownership of objects. If ACLs are disabled as recommended, the bucket owner has full control over every object in the bucket - regardless of who uploaded it.

*Properties* allows you to specify the following

- Storage class (Standard, Intelligent-Tiering, etc.)
- Server-side encryption (specify an encryption key)
- Checksums (to help verify data integrity)
- Tags 
- Metadata

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/a38e2d7c-3573-45c8-9df6-6524e9cd21be/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=60,414)

---
<br>

**3.6.** Click **Upload** to upload the files into the S3 bucket

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e9ca750e-7592-4ae4-be4b-7acb3222e569/ascreenshot.jpeg?tl_px=754,621&br_px=3023,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1002,515)

---
<br>

**3.7.** The green banner at the top indicates that files were successfully uploaded.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/d8e462bb-a4f5-477b-89e1-c0c6bf7f2c42/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=568,520)

---
<br>

**3.8.** Click **Close** to exit this screen and return to the bucket page

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/d7850452-f498-4843-84e5-144f9ffcf25a/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1038,232)


#### Options in S3 Buckets
---
<br>

**3.9.** Explore the additional options available for the bucket. Begin with the first one - Metadata.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/2fb15984-4e71-4f17-834f-d511e4bbe708/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=104,226)

---
### Task 4 - Metadata Options

<br>

**4.1.** Click **Metadata**

We can see that security measures are in place to prevent accessing the metadata configuration. This provides additional security to objects stored in S3. 

Some things to note about the Metadata Tables schema

- Made up of rows and columns 
- Each row represents a mutation event that has created, updated, or deleted an object in your general-purpose bucket 
- Most events are from various user actions, but some of these events are the result of actions taken by Amazon S3 on your behalf. This includes things like S3 Lifecycle expirations or storage class transitions.
- S3 Metadata is an event-processing pipeline

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/c4277c1e-be45-4a09-ba56-c10d3ead0231/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=182,232)

---
## Task 5 - Property Options

<br>

**5.1.** The **Properties** tab includes options to information about the bucket. Information found in this tab includes the following

- AWS Region
- Amazon Resource Name (ARN)
- Creation Date
- Bucket versioning

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/a10b4003-9f8b-4f11-be75-a61b34fa4501/ascreenshot.jpeg?tl_px=0,114&br_px=2752,1653&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=260,277)

---
<br>

**5.2.** You can edit the the **Bucket Versioning** settings by clicking *Edit*

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/fcecd7a5-912b-4152-bed2-6c4d206fab43/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1003,235)

---
<br>

**5.3.** You can choose to Enable bucket versioning (recall, it was left disabled when the bucket was created for this demo).

Once bucket versioning is enabled it cannot be disabled but it can be suspended if needed.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/acd449a2-9743-426e-9301-374450156410/ascreenshot.jpeg?tl_px=0,182&br_px=2752,1721&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=37,277)

---
<br>

**5.4.** If you make changes to versioning, click **Save changes**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/1f93e41f-6d51-4943-8001-8d00ce6397b9/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1027,381)

---
<br>

**5.5.** Continuing with the options under Properties, we see there is a section for **Intelligent-Tiering Archive configuration**. 

Select **Create configuration**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/41e3707f-7f4e-4b83-a82b-a95914fc5431/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=977,344)

---
<br>

<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**5.6.** Intelligent-Tiering Archive configuration is [[a feature that allows you to automatically move objects to more cost-effective archive tiers based on access patterns. It moves objects that have not been access for at least 90 days to archive tiers]]

**Archive Tier Options**

1. Archive Access tier
   - objects are moved here after a minimum of 90 days of no access
   - provides significant savings compared to frequently accessed tier
2. Deep Archive Access tier
   - objects are moved here after a minimum of 180 days of no access
   - provides savings up to 95% compared to standard storage costs.

Learn more at <https://aws.amazon.com/getting-started/hands-on/getting-started-using-amazon-s3-intelligent-tiering/>

---
<br>

**5.7.** To configure, you begin by creating a name for the configuration. The name should be descriptive of its purpose.

Complete information as relevant based on needs.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/6a0a3ff3-b70a-4f3d-9139-ccf34fa244df/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=565,285)

---
<br>

**5.8.** Select appropriate **Archive rule actions** to *Archive Access* tier or *Deep Archive Access* tier.

Objects not accessed for a minimum of 90 consecutive days are automatically moved directly to the Archive Access tier with up to 71% in storage cost savings. 

Objects not accessed for a minimum of 180 days of consecutive days are automatically moved to the Deep Archive Access tier with up to 95% in storage cost savings. 

Click **Create**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e463d701-d772-4b2d-920d-1f35f7bf6b4f/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1051,604)

---
<br>

**5.9.** If the objects are accessed later, S3 Intelligent-Tiering moves the objects back to the Frequent Access tier. To retrieve an object stored in the optional Archive Access tier or Deep Archive Access tier, you must initiate the restore request and wait until the object is moved into the Frequent Access tier.

---
<br>

**5.10.** A green banner indicates that the changes were successfully made.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e6f3d277-6899-411b-91e7-bba910d6afb8/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=998,178)

---
<br>

**5.11.** Use the breadcrumbs to navigate back to the bucket page.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/1b74de3f-6e81-4425-b7d7-44dfc018d0fe/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=261,131)


## Task 6 -  Permission Options

---
<br>

**6.1.** Next, you will go to the **Permissions** tab

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/cf4824d0-b9f4-4000-b28c-ac7c0a8c9131/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=283,229)

---
<br>

**6.2.** The Permissions tab in an S3 bucket is used for managing access control and security settings.

---
<br>

**6.3.** Recall that when this bucket was created, the default settings were left on that blocked all public access.

You can click on the link to expand and view the individual block public access settings for the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/4ed41a90-2f39-4471-95ce-4998c6a03c4c/ascreenshot.jpeg?tl_px=0,193&br_px=2752,1732&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=250,276)

---
<br>

**6.4.** You can customize the level of access for the bucket at a granular level based on the same options as provided when you first created the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/edb85923-315d-45a5-af21-4d5cadd5f197/ascreenshot.jpeg?tl_px=272,204&br_px=3024,1743&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=526,276)

---
<br>

**6.5.** To edit these bucket settings, click on the **Edit** button

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/f0de770e-a31c-4c4d-8c37-dfcf8373de64/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1014,230)

---
<br>

**6.6.** This bucket contains images that we want publicly accessible so uncheck the box that says *Block all public access.* This removes a layer of security of who can access the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e58cdc19-fd83-4f55-ac38-7d910febbda0/ascreenshot.jpeg?tl_px=0,79&br_px=2752,1618&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=88,277)

---
<br>

<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**6.7.** Unchecking "Block all public access" for an S3 bucket is a significant action that should not be taken lightly. 

The "Block all public access" feature was introduced by AWS as a safeguard against the frequent occurrences of data leaks due to misconfigured S3 buckets\[. Disabling it removes this safeguard, so it should only be done with a clear understanding of the potential risks and a strong plan for managing access controls.

Important considerations when unchecking this box.

- Unchecking this option increases the risk of data exposure if proper access controls are not maintained.
- It requires careful management of bucket policies and object permissions to ensure only intended data is made public.
- Public access may be necessary for specific use cases, such as hosting a public website from an S3 bucket. 

In this demo, our bucket contains images that do not require this depth of security and we want available to the public.

---
<br>

**6.8.** Click **Save changes**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/9ddefe1b-0142-42ac-bb1d-ce9fc6aa1d03/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1055,410)

---
<br>

**6.9.** Follow the instructions to confirm the changes

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7da48fa3-bb18-4f70-ac04-b33df0bc2385/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=566,300)

---
<br>

**6.10.** The green banner at the top of the screen confirms the changes were made successfully.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/3d22be47-c070-4862-9267-8d01a7e75e79/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1043,178)

---
<br>

**6.11.** To allow the appropriate access to this bucket, a **Bucket policy** is required. Select the *Edit* button.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/82e7452d-7358-423e-8924-009d98720019/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=959,260)

---
<br>

<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**6.12.** A bucket policy is a resource-based policy that you can use to grant access permissions to your Amazon S3 bucket and the objects in it.

Bucket policies are written in JSON and provide fine-grained control over S3 resources.

Bucket policies are used to

- control access to the bucket and objects in it
- grant or deny permissions on a granular level to AWS accounts, IAM users, or other AWS services
- state the specific conditions as to when to apply the policy (e.g. IP ranges, time of day, etc.)
- can override or supplement access control lists (ACLs) 

**Use Cases for bucket policies**

- Granting cross-account access
- Restricting access to specific IP addresses
- Allowing public access to certain objects

---
<br>

**6.13.** There are a few different ways that you can write the policy.  In this demo, you will click on **Policy generator** which will open a separate tab.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/3a3aaec8-42c0-4bcd-9121-36b95c958795/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=963,200)

---
<br>

**6.14.** For **Select Type of Policy** select *S3 Bucket Policy*

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/5ff41a6b-747d-4ee6-9813-41a04e4593f8/ascreenshot.jpeg?tl_px=0,137&br_px=2752,1676&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=498,276)

---
<br>

**6.15.** The *Principal* is the account, user, role, or service to which the policy applies

An asterisk (\*) can be used as a wildcard which allows anyone to access it.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/ac8e3110-96a5-4400-82e5-08e0accab3a9/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=470,316)

---
<br>

**6.16.** The **Actions** are used to identify what actions the principal can do.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7b4dfb2a-23bd-43d5-bd79-bde79b2c93e4/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=519,399)

---
<br>

**6.17.** Search for and select the **GetObject** option.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/35a949d3-187c-4e26-9dd8-6efe77c5d7e4/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=456,449)

---
<br>

**6.18.** The **GetObject** option is used to grant permission to read (retrieve) objects from the Amazon S3 bucket.

To learn more about different actions, go to <https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazons3.html>

---
<br>

**6.19.** The **Amazon Resource Name (ARN)** is used as a unique identifier for AWS resources and services. 

ARNs are used as a unique identification of AWS resources (You can compare it to your social security number. It provides a unique identification of your identity.)

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7d2dbcb3-fb47-4d73-bbdc-fd2af03936a9/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=417,432)

---
<br>

**6.20.** To find the ARN for this bucket, go back to the S3 console.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/715721e3-0b6b-473d-b78a-5c1ee0466d1d/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=169,5)

---
<br>

**6.21.** Find the **Bucket ARN** and copy the arn code

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7edc2a95-15de-4ba3-a8ce-d82c3148f405/ascreenshot.jpeg?tl_px=0,13&br_px=2752,1552&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=12,277)

---
<br>

**6.22.** Back in the Policy Generator tab, paste the copied ARN into the ARN text box and click **Add Statement**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/7615b3d1-916a-4fb1-9fef-58dc97419cd4/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=463,520)

---
<br>

**6.23.** To create the policy, click **Generate Policy**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/d154a62e-b404-428e-a1ce-80787ee6cee0/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=467,410)

---
<br>

**6.24.** A policy written in JSON is available to be copied.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/8d7c68e2-acb5-4125-a0ef-6537672dc515/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=278,273)

---
<br>

**6.25.** Paste the copied JSON code into the Policy window

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/e8a8955f-83d1-4704-8be8-99bf5bbd456c/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=347,377)

---
<br>

**6.26.** The **Resource** is not yet complete. You need to specify which object(s) in the bucket are accessible in this policy.  If all objects should be accessible, you can use the wildcard by adding a /\* as shown below.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/94cf0f5f-491d-41ca-83b6-334b7c7f1732/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=470,458)

---
<br>

**6.27.** Click **Save changes**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/30894431-00e2-4289-8480-ad4308ba0ad8/ascreenshot.jpeg?tl_px=272,351&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=995,522)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**6.28.** **Structure of a Bucket Policy**

A typical bucket policy includes the following elements:

- *Version*: Specifies the policy language version
- *ID*: An optional identifier for the policy
- *Statement*: One or more individual statements, each containing:
  - *Sid*: An optional statement identifier
  - *Effect*: Specifies whether to Allow or Deny the permissions
  - *Principal*: The account, user, role, or service to which the policy applies
  - *Action*: The list of actions this policy allows or denies
  - *Resource*: The bucket and object resources to which the actions apply
  - *Condition*: Optional conditions for when this policy is in effect

Bucket policies should be carefully crafted to avoid unintended access or security vulnerabilities.

---
<br>

**6.29.** A green banner appears confirming changes were made successfully.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/16371d50-a350-4784-8119-341de302e4bb/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1049,175)

---

## Task 7 -  Object Ownership Options

<br>

**7.1.** **Object Ownership** is an Amazon S3 bucket-level setting that you can use to control ownership of objects uploaded to your bucket. 

It can also be used to disable or enable ACLs

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/312ee491-afe8-4149-a80f-74b517e2e8f8/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=869,319)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**7.2.** Object Ownership is set to the Bucket owner by default and all ACLs are disabled. When ACLs are disabled, the bucket owner owns all the objects in the bucket and manages access to data exclusively policies.

Object Ownership has three settings that you can use to control ownership of objects uploaded to your bucket and to disable or enable ACLs:

1. ACLs disabled (recommended)
   - defaults to bucket owner enforced (bucket owner owns and has full control of every object in the bucket)
2. ACLs enabled - *Bucket Owner Preferred* - bucket owner owns and has full control over new objects that other accounts write to the bucket
3. ACLs enabled - *Object Writer -* the AWS account that uploads an object owns the object, has full control over it and can grant other users access to it via ACLs.

---

<br>

**7.3.** **Access control list (ACL)** are used to manage access to buckets and objects. 

Note - Most modern use cases in Amazon S3 no longer require the use of ACLs and are disabled by default per recommended best practices. It is recommended that IAM or bucket policies are used to control access to objects in the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/62882a9f-1a02-448c-9543-bd9591e6e603/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=858,315)

---
<br>

**7.4.** The **Grantee** information allows you to see permissions based on *Objects* and *Bucket ACL* layers

You see that bucket has the bucket owner enforcement applied to it.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/3bac0f4b-c977-4b32-8e3a-7a05fcbe5eab/ascreenshot.jpeg?tl_px=0,0&br_px=3024,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=669,261)

---
<br>

**7.5.** The Grantee information in Amazon S3 ACLs refers to the entity (user, account, or predefined group) that is granted specific permissions.

When ACLs are disabled in Amazon S3, permissions are still granted through bucket or IAM policies.

---
<br>

**7.6.** The **Cross-origin resource sharing (CORS)** can be used to define a way for client web applications that are loaded in one domain to interact with resources in a different domain.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-07/c2847b2f-b95a-4236-bf64-9eb4843ee722/screenshot.jpeg?tl_px=0,0&br_px=2994,1640&force_format=jpeg&q=100&width=1120.0)

---
<br>

**7.7.** Cross-Origin Resource Sharing (CORS) is an important security feature implemented by web browsers to protect users from potentially malicious cross-origin requests.

Amazon S3 supports CORS configuration for buckets, allowing you to control which web applications can access your S3 resources. This is useful when hosting static websites on S3 or when building a client-side web applications that interact with S3 buckets.

**Benefits of CORS**

1. Enables secure cross-origin requests and data transfers between browsers and servers
2. Allows web applications to access resources from different domains
3. Provides a way for servers to specify which origins are allowed to access their resources

---

## Task 8 -  Metrics Options


**8.1.** The Metrics tab provides information on the usage, performance, and health of your S3 buckets. They become available about 15 minutes after configuration.

By leveraging these metrics, you can gain insights into your S3 usage, optimize performance, and make informed decisions about your storage strategy.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/c2a1e917-df4f-4435-8afe-45fe7cb118e7/ascreenshot.jpeg?tl_px=0,114&br_px=2752,1653&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=423,277)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">


**8.2.** Amazon S3 offers three main types of metrics:

1. *Storage metrics:* Reported daily at no additional cost
   - monitors bucket storage using CloudWatch
   - collects and processes storage data from Amazon S3 into readable, daily metrics
   - are reported once per day and are provided to all customers at no additional cost
2. *Request metrics:* Available at 1-minute intervals, billed at standard CloudWatch rates
   - monitor S3 requests to quickly identify and act on operational issues
   - available at near real-time 1-minute intervals after (some latency for processing)
   - CloudWatch metrics are billed at the same rate as the Amazon CloudWatch custom metrics
   - metrics are reported for all object operations
   - metrics are available at the bucket level by default
   - can define a filter for the metrics using a shared prefix, object tag, or access point
3. *Replication metrics:* For monitoring replication rules and progress
   - monitors the following
     - total number of S3 API operations that are pending replication
     - the total size of objects pending replication
     - the maximum replication time to the destination AWS Region
     - the total number of operations that failed replication

The benefits of Bucket Metrics are as follows

- monitor bucket usage and performance
- identify operational issues quickly
- track costs associated with different storage classes
- ensure compliance with data lifecycle policies

---
<br>

**8.3.** The **Storage Class Analysis** is used to analyze storage access patterns. This helps you decide when to transition the right data to the right storage class.

Note - Storage class analysis only provides recommendations for Standard to Standard IA classes.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/8bed352d-c9de-443e-b475-5d2d5df767bb/ascreenshot.jpeg?tl_px=0,260&br_px=2752,1799&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=378,276)

---
<br>
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Tip icon" width="240" height="100" style="vertical-align: middle;">

**8.4.** With **Replication Metrics**, you can monitor the progress of replication. It tracks the following

-  bytes pending
- operations pending
- and replication latency

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-07/c14714f6-e533-4837-8479-64295f501815/screenshot.jpeg?tl_px=0,0&br_px=2994,1640&force_format=jpeg&q=100&width=1120.0)

---
## Task 9 - Management Options

<br>

**9.1.** Click on the **Management** tab provides options for configuring various aspects of bucket management and optimization

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/2d6beb75-1fe5-4a40-821e-db5d08b2b56a/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=483,230)

---
<br>

**9.2.** In the Management tab you will be able to configure the following

- lifecycle rules
- replication rules
- inventory configurations

---
<br>

**9.3.** Under Management, the **Lifecycle configuration** is used to create a set of rules that define actions that Amazon S3 applies to a group of objects. 

Lifecycle rules run once per day.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/c260bc2f-0480-45d9-b098-8d8748db5ef0/ascreenshot.jpeg?tl_px=0,164&br_px=2752,1703&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=464,277)

---
<br>

**9.4.** To create a lifecycle rule, click **Create lifecycle rule**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/ab84bfcb-0d90-4b03-a22c-9fed56d35fa2/ascreenshot.jpeg?tl_px=272,254&br_px=3024,1793&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=941,277)

---
<br>

**9.5.** Provide a descriptive name for the lifecycle rule.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/67686d2d-c885-48d4-ac14-3e1b1e534f94/ascreenshot.jpeg?tl_px=253,27&br_px=3005,1566&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)

---
<br>

**9.6.** **Choose a rule scope** based on need. Options include

*Limit the scope of this rule using one or more filters* is used to limit to all objects with a specific prefix or tag.

*Apply to all objects in the bucket* is used to apply to all objects in the bucket.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/5bf35686-1cfd-4037-84b0-60b0b203d5ae/ascreenshot.jpeg?tl_px=0,228&br_px=2752,1767&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=154,276)

---
<br>

**9.7.** Confirm as necessary

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/f44e6928-2201-419b-b146-1989ad66210c/ascreenshot.jpeg?tl_px=0,319&br_px=2752,1858&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=41,276)

---
<br>

**9.8.** **Lifecycle rule actions** are used to set the actions that this rule policy will perform.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/1f1c35e2-5eec-407b-9b8e-0d455cfdae00/ascreenshot.jpeg?tl_px=0,147&br_px=2752,1686&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=3,277)

---
<br>

**9.9.** Confirm changes

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/85c27315-aea3-4b17-8303-d1a4c3b6ca78/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=38,295)

---
<br>

**9.10.** **Transition current version of objects between storage classes** is used to move the current version of objects.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/30e4238e-f8f3-401c-813e-05ea8ba7e85e/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=487,303)

---
<br>

**9.11.** **Transition noncurrent versions of objects between storage classes** is used to move the previous (noncurrent) versions of an object.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/f1f01679-d0de-436c-a93f-6eccb6528b40/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=368,284)

---
<br>

**9.12.** Set the days as appropriate based on needs. Remember that multiple versions will increase your usage of the storage service and your bill.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/2c8ee6f1-72e1-4294-9404-873024b99ab9/ascreenshot.jpeg?tl_px=0,351&br_px=2752,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=412,318)

---
<br>

**9.13.** Click **Create rule**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/b260bd04-546f-4f9a-8f5c-5cb5e7b8ebd7/ascreenshot.jpeg?tl_px=754,621&br_px=3023,1890&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1017,511)

---
<br>

**9.14.** Green banner confirms the rule was created.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/80a180ee-99eb-4ce4-b4c8-b4b19bca2d6a/ascreenshot.jpeg?tl_px=272,0&br_px=3024,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=1050,178)

---
<br>

**9.15.** Click here

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/5807393b-4c37-4a91-b01f-338b928f8d04/ascreenshot.jpeg?tl_px=0,0&br_px=2752,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=253,132)

---
## Task 10 -  Replication of Objects
<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**10.1.** There are two types of replication: *live replication* and *on-demand replication*.

- **Live replication** 

  - replicates objects in the destination bucket(s) as they are written in the source buckets 
  - doesn't replicate any objects that existed in the bucket before you set up replication.

- **On-demand replication** 

  - replicates existing objects from the source bucket to one or more destination buckets on demand

There are two forms of live replication: *Cross-Region Replication (CRR)* and *Same-Region Replication (SRR)*.

- **Cross-Region Replication (CRR)** – You can use CRR to replicate objects across Amazon S3 buckets in different AWS Regions.

- **Same-Region Replication (SRR)** – You can use SRR to copy objects across Amazon S3 buckets in the same AWS Region.

---

<br>

**10.2.** **Replication rules** are used to enable automatic, asynchronous copying of objects across Amazon S3 buckets.

**Inventory configuration** is used to help manage your storage. It can also help simplify and speed up business workflows and big data jobs

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-07/68f91f96-2646-4713-b5b9-6813bab335cf/screenshot.jpeg?tl_px=0,0&br_px=2994,1640&force_format=jpeg&q=100&width=1120.0)

---
<br>

<img src="https://github.com/user-attachments/assets/967ad973-e8bf-4d94-bd3b-90ea104e1dc6" alt="Learning on the Lab" width="240" height="100" style="vertical-align: middle;">

**10.3.** Buckets configured for object replication can be owned by the same AWS account or by different accounts.

You can replicate objects to a single destination bucket or to multiple destination buckets.

The destination buckets can be in different AWS Regions or within the same Region as the source bucket.


Tip: **Replication can help you do the following:**

1. Replicate objects while retaining metadata 
2. Replicate objects into different storage classes 
3. Maintain object copies under different ownership 
4. Keep objects stored over multiple AWS Regions
5. Replicate objects within 15 minutes

---
## Task 11 - Access Points


**11.1.** Access Points in Amazon S3 are unique network endpoints that simplify data access for shared datasets in S3 buckets. They provide a flexible way to manage access to your S3 data at scale.

---
<br>

**11.2.** Click the **Access Points** tab

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/6f68b2e8-5492-4d31-978f-29f6a32169e2/ascreenshot.jpeg?tl_px=223,0&br_px=2975,1538&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=523,232)

---
<br>

**11.3.** This demo is not going to create an access point but you can see the button to begin. Learn more about access points at <https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-access-points.html>

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-02-06/dcc7a62d-622f-49c3-8f97-9438fd53fd40/ascreenshot.jpeg?tl_px=0,124&br_px=2752,1663&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=456,277)
#### [Made with Scribe](https://scribehow.com/shared/Create_an_Amazon_S3_Bucket__b-l-u_DgTQCxfPHVWi9WhA)


