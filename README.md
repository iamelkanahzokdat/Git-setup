# Git-setup
This document provides a brief summary of my present knowledge and configuration of git and version control based on today’s lesson. Our teacher, Mr. Bankat, discussed everything essential for beginners in our introduction to git. Before we begin, let’s examine some fundamental concepts.

What is Version Control?  
Version control is a mechanism that keeps track of changes made to files over time, enabling you to observe alterations, revert to previous versions, and work with others without losing progress.

Importance of Version Control  
It helps in managing a project's history.  

It enables collaboration on code with several contributors.  

It allows reversion to earlier versions if problems occur.  

It supports safe experimentation with new features.  

It assists in displaying the head and branches of a project.  

What is Git?  
Git is a decentralized system for version control that monitors code changes and facilitates collaboration with others. It operates locally on your computer and allows effective management of project versions. It can also be considered a version control method that aids in storing files remotely.

Difference Between Git and GitHub  

| Git | GitHub |  
| --- | --- |  
| A software tool installed on your machine for managing version control. | An online platform for hosting and sharing Git repositories. |  
| Functions offline. | Requires an internet connection. |  
| Tracks the code's history. | Enables collaboration, pull requests, and project management. |  

Git and GitHub Setup for Beginners (Ubuntu)  
Using SSH with GitHub enhances both the security and convenience of authentication. Here’s how I set it up:  
Step 1: Install Git  
''' sudo apt update  
sudo apt install git '''  
Step 2: Register for a GitHub account  
Go to https://github.com and create an account.  

Step 3: Configure Git with your identity  
''' git config --global user.name "Your Name"  
git config --global user.email you@example.com '''  
Step 4: Generate an SSH Key  
This creates a pair of public and private SSH keys.  
''' ssh-keygen -t ed25519 -C "you@example.com" '''  
Press Enter to confirm the default file location, and then either provide a passphrase or leave it blank.  

Step 5: Add the SSH Key to the SSH Agent  
''' eval "$(ssh-agent -s)"  
ssh-add ~/.ssh/id_ed25519 '''  
Step 6: Connect Your SSH Key with GitHub  
Copy your public key:  
''' cat ~/.ssh/id_ed25519.pub '''  
Visit GitHub:  

Click on your profile → Settings → SSH and GPG keys → New SSH key  

Insert the key you copied and save it.  

Step 7: Test SSH Connection with GitHub  
''' ssh -T git@github.com '''  
Step 8: Create a New Repository on GitHub  
Go to GitHub → New Repository → name it and create it.  

Step 9: Initialize Git in Your Project Folder  
''' cd your-project-folder  
git init '''  
Step 10: Link Local Folder to GitHub Using SSH URL  
Get your SSH URL from GitHub (it will look like git@github.com:username/repo.git), and then:  
''' git remote add origin git@github.com:username/repo.git '''  
Step 11: Add, Commit, and Push Code  
''' git add .  
git commit -m "Initial commit"  
git branch -M main  
git push -u origin main '''  

Your project is now securely connected to GitHub using SSH!
