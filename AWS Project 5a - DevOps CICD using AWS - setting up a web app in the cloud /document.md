AWS project 5a - DevOps CI/CD
Setting Up a Web App in the Cloud



This project is the first step in a seven-project series that will guide you through the process of creating a Continuous Integration and Continuous Deployment (CI/CD) pipeline to build and deploy a web application using AWS services. The primary goal of this project is to set up a web application in the cloud using Amazon EC2, which will lay the foundation for more advanced DevOps practices, including the use of AWS Code services for CI/CD in subsequent projects.
In this step, you will learn how to launch an EC2 instance, connect to it using SSH, and configure the instance with necessary software like Java and Maven to generate a basic web app. You will also set up your development environment with Visual Studio Code (VSCode), connecting it remotely to your EC2 instance to edit and manage your application files.

AWS Services Used

1. Amazon EC2
Amazon Elastic Compute Cloud (EC2) is a web service that provides resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers by providing flexible and scalable instances that run on-demand. In this project, EC2 will host the web app that you'll build and deploy.

2. VSCode
VSCode is a lightweight code editor that allows developers to edit code and manage files in real-time. With the help of the Remote - SSH extension, VSCode can connect to your EC2 instance, making it easier to work directly on your application without needing to manage files manually through SSH commands.

Instructions

Step 1: Launch an EC2 Instance
1. Sign in to AWS Management Console Log in to the AWS console to access the EC2 service.
2. Go to the EC2 Dashboard and click on "Launch Instance" Navigate to the EC2 Dashboard to start the process of launching an instance.
3. Configure the Instance
    * Name and Tags: Provide a name for your instance, such as "MyDevOpsInstance" for easy identification.
    * Application and OS Images: Select the latest Amazon Linux 2 AMI to use a lightweight, secure, and stable operating system.
    * Instance Type: Choose the t2.micro type for a low-cost instance with adequate resources for this web app.
    * Key Pair: Create a new key pair for SSH access to the instance and download it (e.g., nextwork-keypair.pem).
    * Security Group: Open necessary ports like SSH (22), HTTP (80), and HTTPS (443) to allow access.
4. Launch the Instance Click "Launch" to initialize the instance, then note the Public IPv4 DNS for SSH connection.



Step 2: Connect to Your EC2 Instance
1. Open a terminal on your local machine Prepare your terminal to execute SSH commands to access the EC2 instance.
2. Navigate to the directory containing your .pem file Go to the folder where your private key (.pem file) is stored to use it for authentication.
3. Modify the permissions of your .pem file Run chmod 400 nextwork-keypair.pem to secure the key and ensure only you can access it.
4. Connect to your EC2 instance via SSH Run the SSH command (ssh -i "nextwork-keypair.pem" ec2-user@[YOUR PUBLIC IPV4 DNS]) to log in securely to the EC2 instance.



Step 3: Install Java Development Kit (JDK)
1. Update the package list Run sudo yum update -y to ensure the latest software packages are available.
2. Install the JDK Run sudo amazon-linux-extras install java-openjdk11 -y to install Java, necessary for building Java-based applications.
3. Verify the installation Run java -version to check that Java has been successfully installed.



Step 4: Install Maven
1. Install Maven Run sudo yum install maven -y to install Maven, a build automation tool used for Java applications.
2. Verify the installation Run mvn -version to confirm that Maven is correctly installed.



Step 5: Create a Directory for Your Web App
1. Create a new directory for your project Run mkdir ~/nextwork-web-project to create a directory where you’ll store your web app files.
2. Change to that directory Run cd ~/nextwork-web-project to navigate into the newly created directory.



Step 6: Create the Application
1. Generate a web app using Maven Run mvn archetype:generate -DgroupId=com.nextwork.app -DartifactId=nextwork-web-project -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false to create a basic Java web application using Maven's archetype plugin.
2. Confirm successful project creation Look for the "BUILD SUCCESS" message in the terminal to ensure the app was created successfully.


Step 7: Connect VSCode with Your EC2 Instance
1. Open VSCode on your local machine Launch VSCode to edit your code locally while interacting with your EC2 instance.
2. Install the Remote - SSH extension Install the "Remote - SSH" extension in VSCode to connect to your EC2 instance from within the editor.
3. Set up a connection to your EC2 instance Click the Remote-SSH icon, then add the SSH host using the command: ssh -i /path/to/nextwork-keypair.pem ec2-user@[YOUR PUBLIC IPV4 DNS] to securely connect to your EC2 instance.
4. Open your web app’s files In VSCode, select "Open Folder" and navigate to /home/ec2-user/nextwork-web-project to open the project folder stored on your EC2 instance.
5. Trust the files When prompted, click “Yes, I trust the authors” to allow VSCode to work with the files.


Final Step: Edit index.jsp
1. Open index.jsp Navigate to the file located at src/main/webapp/index.jsp to edit the main page of your web app.
2. Modify the file Replace the existing code with a simple greeting message and save the changes: html Copy code   <html>
3. <body>
4. <h2>Hello {YOUR NAME}!</h2>
5. <p>This is my NextWork web application working!</p>
6. </body>
7. </html>
  
Save the changes Press Command/Ctrl + S to save the modified index.jsp file with your new content.

In this project, we successfully set up a basic web application hosted on an Amazon EC2 instance. We launched the EC2 instance, connected to it via SSH, and installed the necessary tools like Java and Maven to support the application. After creating a simple web app using Maven, we connected VSCode to our EC2 instance for convenient file editing and deployed the app.
This foundational setup is an important step in building and deploying web applications in the cloud, and it lays the groundwork for further DevOps and CI/CD work in upcoming projects.
