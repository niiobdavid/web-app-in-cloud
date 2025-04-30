<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Nii OB  
**Email:** davidniiamui@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, we're going to set up a web app in the cloud using AWS and VSCode. This work lays the foundation for our DevOps (CI/CD pipeline) series.

### Key tools and concepts

VSCode is not an AWS service but it is an incedibly popular and versatile and popular IDE i.e. a tool for creating, editing and managing software.

### Project reflection

One thing I didn't expect was the ability to use VSCode like a local IE for a remote server. 
Downloading Remote - SSH is a game changer.

This project took me 2.5hours including documentation and troubleshooting time.
Seeing a successful SSH connection to my EC2 instance was most rewarding, be it over terminal or VSCode SSH connection.

VSCode played a key part in today's project as I used it to connect with my EC2 instance, run the commands for installing tools like Maven & Java and set up a Java web app.

---

## Launching an EC2 instance

I started this project by launching an EC2 instance because I want the web app to live entirely in the cloud, so I'm launching an EC2 instance to develop the web app's code.

### I also enabled SSH

SSH (Secure Shell) is a protocol that makes sure communication between servers (connected remotely) is authorized and secure (encrypted).
I enabled my ssh traffic from just my IP address so that I can connect to my EC2 instance in the next step.

### Key pairs

A key pair is like a lock and key for our EC2 instance. It is used for authentication i.e. for us to securely get access to our EC2 instance. It works by having 2 halves: a private and public key that must match up in order to get access.

Once I set up my key pair, AWS automatically downloaded a file called nextwork-keypair.pem.
This file is my private keypair, i.e. my half of the key pair that I will need to access my EC2 instance later in this project.

---

## Set up VS Code

VSCode is an IDE (software for editing and creating code) and is also one of the most popular editors as it comes with a massive library of extensions and is compatible with different languages and use cases.

I installed VSCode to connect to the EC2 instance and then create and edit web app files on that EC2 instance.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal lets users execute text-based commands to control their computer or server. It's an alternative to using clicks and drags. The first command ran in this project was cd ~/Desktop/DevOps which changes the directory to the DevOps folder(keys)

I updated my private key's permissions using the `icacls` command: `icacls "nextwork-keypair.pem" /reset`, `icacls "nextwork-keypair.pem" /grant:r "USERNAME:R"`, and `icacls "nextwork-keypair.pem" /inheritance:r` to grant read perm- and block others.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

To connect to my EC2 instance, I ran the command 'ssh -i [PATH TO .PEM FILE] ec2-user@[IPV4 DNS of the EC2 INSTANCE]'.
This command set up an SSH connection that uses the .pem file (my private key) and the public address of the EC2 instance.

### This command required an IPv4 address

A server's IPv4 DNS is its public address.
Computers/ servers connected to the internet can use the Public IPv4 DNS to find and locate another server.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

Apache Maven is a tool/package manager for the building process of software.
The building process involves compiling and packaging code, so it can be hosted on a server, etc.

Maven is required in this project because it is extremely helpful for bringing in packages into our application (i.e.external software/tools) and for packaging up our own web app once we've developed it.

Java is a programming language used to develop all kinds of applications.
We downloaded Amazon Correto 8, which is a specific version of Java that's managed by Amazon/AWS.

Java is required in this project because we want to build a Java web app and we will need to install it first in order to run any Java commands.

---

## Create the Application

I generated a Java web app using the command 'mvn archetype:generate' which is a command that sets up a basic web app (using Maven's archetype template).

I installed Remote - SSH, extension to connect VSCode directly to the EC2 instance.
Doing this means I can later use VSCode as an IDE for the Java web app files in the EC2 instance.
This makes editing the web app much simpler/ more efficient.

Configuration details required to set up a remote connection include the SSH Host's name (i.e. the IPv4 DNS of the EC2 instance), the location of the private key on my local computer, and the SSH Host's user I am connected to.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

Using VSCode's file explorer, I could see at a glance, a file tree of all the sub folders and files that make up the nextwork-web-project folder for the Java web app.

Two of the project folders created by Maven are src and webapp. 
src contains all of the web app's source code (i.e. the code that defines the web app's look and feel), whereas web app is a subfolder of src that focuses on what the user would see.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

index.jsp is afile within the web app folder, and it defines the look of a Java web app.

I edited index.jsp by using VSCode.
Even though index.jsp is stored in my EC2 instance, because I've set up a Remote - SSH connection between VSCode and the instance, I can use VSCode like a local IDE  for my instance.

![Image](http://learn.nextwork.org/genuine_navy_mysterious_monkey/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

---

---
