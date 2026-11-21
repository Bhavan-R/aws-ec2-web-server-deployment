# AWS EC2 Web Server Deployment

**Module:** AWS IAM & EC2 (Day 6–Day 10)  
**Level:** Beginner

## Project overview
A beginner project demonstrating IAM fundamentals, EC2 instance launch, security-group configuration, and hosting a static HTML website using a web server.

## Objectives
- Explore IAM users, groups, roles, policies, and permissions.
- Understand basic cloud security and least privilege.
- Launch and configure an Amazon EC2 instance.
- Configure a security group and connect to the instance.
- Install a web server and deploy a basic HTML site.

## Technologies / AWS services
- AWS Identity and Access Management (IAM)
- Amazon EC2
- EC2 Security Groups
- Linux
- Apache HTTP Server
- HTML and CSS

## Website
The static website is `index.html`.

## Deployment outline
1. Sign in to AWS Console and open EC2.
2. Launch a Linux instance. Choose an eligible instance type and review costs before launch.
3. Create/select a security group. Allow HTTP (TCP 80) from `0.0.0.0/0` so the public site can load. Restrict SSH (TCP 22) to **your own IP address** only; do not expose SSH to everyone.
4. Connect using EC2 Instance Connect or SSH.
5. On Amazon Linux, install Apache with:
   ```bash
   sudo dnf update -y
   sudo dnf install -y httpd
   sudo systemctl enable --now httpd
   ```
   (If using a different Linux distribution, use its package manager and service name.)
6. Upload/copy `index.html` to Apache's web root:
   ```bash
   sudo cp index.html /var/www/html/index.html
   ```
7. In a browser, visit `http://YOUR-EC2-PUBLIC-IP/` and verify the site.
8. Capture your own screenshots of IAM, instance details, security-group rules, and the working public website for your submission.

## Security notes
- Never commit AWS credentials, access keys, private keys, passwords, or `.pem` files.
- Use least privilege and restrict SSH access to your IP.
- Review AWS pricing and free-tier/credit eligibility before launching resources.
- Stop or terminate resources when finished to avoid ongoing charges; terminating deletes the instance's local data unless saved elsewhere.

## Deliverables checklist
- [ ] GitHub repository containing this project
- [ ] Public live website URL (after successful AWS deployment)
- [ ] LinkedIn post link

## Repository structure
```text
aws-ec2-web-server-deployment/
├── index.html
├── README.md
├── LINKEDIN_POST.md
└── screenshots/
    └── (add your project screenshots here)
```

## Project status
Website files are prepared. AWS deployment, screenshots, repository publication, and public URL still need to be completed by the account owner.
