 Backup and Restore EC2 Server

## Objective 

The goal of this project is to backup and restore data on the EC2 instance 

## Pre-requisities 

- An AWS account
- Basic Understanding of AWS  service
- Familiarity with SSH

### Step 1: Create and SSH into EC2 instance 

1. **Login to the AWS Console**: Navigate to the AWS Management Console and sign in
2. **Navigate to EC2 Dashboard**: Go to Services > EC2.
3. **Launch New Instance**: Click on the "Lauch Instance" button.
4. **Configure Instance**: Select an AMI, instance type, and other configurations as per you needs.
5. **Security Group**: Ensure to allow SSh traffic in the security group settings
6. **Create Key Pair**: Make sure you create a key pair if you have not already created one
7. **Launch Instance**: Review and launch the instance.
8. **SSH into Instance**: Use the `ssh` command to SSH into your instance.

    ```bash
    ssh -i "your-ssh-key.pem" ec2-user@your-ec2-ip-address
    ```
---

### Step 2: Create 'example.txt' and a text of choice "This is an examplet txt file"

1. **Create File**: Use the `touch` command to create a new file named 'example.txt'.

    ```bash
    nano example.txt
    # OR
    vim example.txt
    ```
2. **Edit File**: Use a text editor like `nano` or `vi` to edit the file.

    ```bash
    nano example.txt
    # OR
    vi example.txt
    ```
3. **Write Content**: Write "This is an examplet txt file" into the file and save it.

---

### Step 3: Take an image of the instance

1. **Navigate to EC2 Dashboard**: Go to Service > EC2.
2. **Select Instance**: Locate and select your EC2 instance.
3. **Create Image**: Go to "Actions" and select "Create Image".
4. **Configure Image**: Provide an image name and description.
5. **Create**: Click "Create Image".

---

### Step 4: Create a new EC2 instance from the image 

1. **Navigate to AMI Section**: Go to EC2 Dashboard > AMIs.
2. **Select Your Image**: Choose the image you just created.
3. **Launch Instance**: Click "Launch Instance".
4. **Configure New Instance**: Follow the same steps as in Step 1 to configure and launch the new instance.

---

### Step 5: Verify by SSHing into the new instance and checking for 'example.txt'

1. **SSH into New Instance**: Use the `ssh` command to SSH into the new instance.

    ```bash
    ssh -i "your-new-ssh-key.pem" ec2-user@your-new-ec2-ip-address
    ```

2. **Check for File**: Use the `ls` command to verify the presence of `example.txt`.

    ```bash
    ls
    ```

3. **Verify Content**: Use the `cat` command to check the content of `example.txt`.

    ```bash
    cat example.txt
    ```

