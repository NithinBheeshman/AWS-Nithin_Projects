
Step 1: Connect to Your EC2 Instance
Launch VS Code and open a new terminal. Use the SSH command to connect to your EC2 instance. Replace ec2-userand your-ec2-instance-public-ip with your EC2 username and public IP address:
ssh ec2-user@your-ec2-instance-public-ip
Once connected, you should see the terminal prompt change to indicate you're now operating on the EC2 instance.
Step 2: Install Git
Update the package list by running the following command to ensure your package list is up to date:
sudo yum update -y
Install Git by running the following command:
sudo yum install git -y
Verify Git installation by running the following command:
git --version
Step 3: Clone Your GitHub Repository
Navigate to your desired directory using the cd command:
cd /path/to/your/directory
Clone your repository by running the following command. Replace your-github-repo-url with your repository's URL:
git clone your-github-repo-url
Navigate into the cloned repository using the cd command:
cd your-repo-name
Step 4: Make Initial Commit and Push
Create a new file named index.jsp in the repository:
echo '<html><body><h1>This is my NextWork web application working!</h1></body></html>' > src/main/webapp/index.jsp
Stage the new file by running the following command:
git add src/main/webapp/index.jsp
Commit the new file with a message:
git commit -m "Add initial index.jsp"
Push the commit to the remote repository:
git push -u origin master
Step 5: Set Up Your Git Identity
Set your Git username by running the following command. Replace Your Name with your actual name:
git config --global user.name "Your Name"
Set your Git email by running the following command. Replace you@nextwork.org with your actual email address:
git config --global user.email you@nextwork.org
Step 6: Set Up a GitHub Token
Generate a GitHub token by heading to GitHub, going to your profile icon, and selecting Settings. Navigate to Developer settings at the bottom of the left-hand panel. Select Personal access tokens, then Tokens (classic), and Generate new token (classic). Give your token a note like "Generated for EC2 Instance Access" and set the expiration to 30 days. Select the repo scope. Generate and copy the token. Keep it safe; you won't be able to see it again once you close the tab.
Switch back to your VS Code terminal. Run git push -u origin master again. Enter your GitHub username. When prompted for a password, paste in your token and press Enter.
Go to your GitHub repository in your browser and refresh the page to see your web app files and commit message.
Step 7: Your Second Commit
In VS Code, find index.jsp in your file navigator. Add the following line below the existing line:
<p>If you see this line in GitHub, that means your latest changes are getting pushed to your cloud repo :o</p>
Save your changes.
Stage your changes by running the following command in the terminal:
git add .
Review staged changes by running the following command:
git diff --staged
Commit the changes with a message:
git commit -m "Add new line to index.jsp"
Push the changes:
git push
If prompted, enter your username and token again.
Go to your GitHub repository in your browser and refresh the page to see the updated index.jsp.

