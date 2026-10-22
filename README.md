# How to Launch an AWS EC2 Instance

A beginner-friendly, step-by-step guide to launching an Ubuntu EC2 instance on the AWS Free Tier and connecting to it.

📄 **Visual guide with screenshots:** [EC2_LinkedIn_Carousel.pdf](EC2_LinkedIn_Carousel.pdf)

## What you will learn

- Launching an Ubuntu EC2 instance on the Free Tier
- Creating a key pair (`.pem`) for secure access
- Configuring a security group (firewall)
- Connecting to your instance from the AWS Console

## Prerequisites

- An AWS account
- Basic familiarity with the AWS Management Console

## Steps

### 1. Search for EC2
Log in to the AWS Console and type **EC2** in the search box at the top.

### 2. Open the EC2 service
Click **EC2** in the search results to open the EC2 dashboard.

### 3. Go to Instances
In the left navigation bar, click **Instances**.

### 4. Click Launch instances
On the Instances page, click the orange **Launch instances** button at the top right.

### 5. Name your instance
Type a name for your instance in the **Name** field.

### 6. Choose an AMI
Under Application and OS Images (Amazon Machine Image), select **Ubuntu** and pick a version marked **Free tier eligible**.

### 7. Pick the instance type and key pair
Choose a **Free tier eligible** instance type (for example, `t2.micro` or `t3.micro`, depending on your region). Then click **Create new key pair** to generate your private key.

### 8. Create the key pair
- Enter a key pair name
- Key pair type: **RSA**
- Private key file format: **.pem**
- Click **Create key pair**

The private key downloads to your computer automatically. Store it somewhere safe. You cannot download it again.

### 9. Set up the firewall
Under Network settings, choose **Create security group** (or select an existing one) and set the rules you need. Then click **Launch instance** at the bottom right.

### 10. Instance launched
Your instance is now launching. Click **Instances** to go back to the instance list.

### 11. Select and connect
Tick the checkbox next to your instance and click **Connect** at the top right.

### 12. Connect to the instance
Keep the default settings in the window that opens and click **Connect** at the bottom right.

### 13. You're in!
A terminal opens in your browser and you can start working on your instance.

## Optional: connect from your own terminal with SSH

```bash
chmod 400 your-key.pem
ssh -i your-key.pem ubuntu@<your-instance-public-ip>
```

The default username for Ubuntu AMIs is `ubuntu`. Make sure your security group allows inbound **SSH (port 22)**.

## Security tips

- **Never commit your `.pem` file to GitHub.** Add `*.pem` to your `.gitignore`.
- Restrict SSH access in your security group to **My IP** instead of `0.0.0.0/0` when possible.
- Do not share your AWS account ID or access keys in screenshots or code.

## Clean up to avoid charges

When you are done practicing, select your instance, then choose **Instance state → Terminate instance**. Stopped instances can still incur storage charges; terminated instances do not.

## Author

**Saurabh Naikwadi**: learning Cloud and DevOps Engineering
Connect with me on LinkedIn.

If this guide helped you, give the repo a ⭐
