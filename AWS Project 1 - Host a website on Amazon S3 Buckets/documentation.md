AWS Project 1 - Host a Website on Amazon S3 Buckets

Amazon S3:

For this project, I used Amazon Simple Storage Service (S3) to host a static website. Amazon S3 is a highly reliable, scalable, and high-speed cloud storage service that is ideal for storing and serving static content such as HTML files, images, and videos. The platform provides easy management of these resources while ensuring durability and performance, making it a perfect solution for hosting static websites.

In this project, my goal was to host a basic static website, which includes an index.html file and associated website assets (like images). Amazon S3 is not only cost-effective but also offers ease of use and the ability to handle large amounts of traffic due to its scalability.

Overview:

The project was simple yet educational. In just under 10 minutes, I created a fully functional static website hosted on Amazon S3. The process was straightforward, but there was a crucial learning moment along the way when I realized that S3 buckets are private by default. This meant that access to the website was initially blocked, requiring a quick solution to make the content publicly accessible.

Steps to Host the Website:

1. Creating the S3 Bucket:


To begin, I created a new S3 bucket to store my website files. Amazon S3 requires the bucket name to be unique across all S3 buckets globally, which meant I had to come up with a distinct name. I also chose the AWS region that was closest to my location for better performance.

Creating the bucket itself was a fast process, taking less than 2 minutes. I just followed the on-screen prompts and selected the default settings for the bucket. It was quite simple and didn't involve much setup.

![Website Screenshot](images/Screenshot\ 2024-11-22\ at\ 2.49.54\ PM.png)



2. Uploading Files to S3:

Once the bucket was created, I proceeded to upload my website files. This included the index.html file (the main page of my website) and other assets such as images that were used within the HTML. The process of uploading files was as easy as dragging and dropping them into the S3 console, and it didn't take long at all.

3. Making Files Public:

Here’s where I ran into my first challenge. By default, all objects stored in an S3 bucket are private, meaning only the owner (me) can access them. Since I was building a public-facing website, this wasn't ideal. I needed to configure the files to be publicly accessible.

I quickly learned that to make the website accessible to others, I needed to modify the Access Control List (ACL) settings for each file. This involved allowing public read access for the files, which I did through the S3 console. Once this change was made, the website could be viewed by anyone with the URL.

4. Enabling Static Website Hosting:

After ensuring that the files were publicly accessible, the next step was to enable static website hosting for my S3 bucket. Amazon S3 supports static website hosting, and enabling this feature provides an automatically generated URL that points to the root of the website (usually index.html).

To enable this, I navigated to the “Properties” tab of the S3 bucket, found the “Static website hosting” section, and selected the option to enable it. I also specified the index.html file as the default document. After saving the settings, S3 generated a URL that could be used to access the static website.

5. Resolving the Connection Error:

At this point, I tried accessing the URL that Amazon S3 had generated, but I was met with an "Access Denied" error. This was due to the default private settings of the objects in the bucket, which were not set to be publicly accessible.

To fix this, I went back to the S3 console, selected the files in the bucket, and used the ACL settings to allow public read access to all files within the bucket. Once this was done, I reloaded the page, and the website loaded successfully.

6. Final Result:

With the issue resolved, I was able to access the website via the public URL that Amazon S3 had provided. The website was now live, hosted entirely on S3, and accessible to anyone with the link. The process was quick and efficient, and I now had a working static website hosted on the cloud.

This project not only helped me get hands-on experience with S3 but also taught me how to handle common issues like setting up public access for a static website. It's a great introduction to AWS services, and the fact that it only took about 10 minutes to set up made it a perfect starting point for exploring other AWS features.
