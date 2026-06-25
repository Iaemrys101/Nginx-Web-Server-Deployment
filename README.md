# Nginx Web Server Deployment

A production-ready nginx web server deployed on AWS EC2, serving a Bootstrap personal portfolio website.

##  What's Running

- **Web Server:** Nginx
- **Platform:** AWS EC2 (Ubuntu 26.04 LTS)
- **Instance Type:** t3.micro
- **Status:** Live & Running

##  Live Website

Visit: `http://13.41.109.132`

##  Setup Steps

### 1. EC2 Instance & SSH
```bash
# Connect to your EC2 instance
ssh -i "your-key.pem" ubuntu@your-public-ip
```

### 2. Verify Nginx is Running
```bash
# Check nginx status
sudo systemctl status nginx

# Verify it's listening on port 80
sudo ss -tlnp | grep :80
```

### 3. Web Content Location
```bash
# Default nginx web directory
/var/www/html/

# Check deployed files
ls -la /var/www/html/
```

### 4. Test the Server
```bash
# Local test
curl localhost

# Remote test (replace IP with yours)
curl http://13.41.109.132
```

##  Security Configuration

**Inbound Rules (Security Group):**
- HTTP (Port 80) — Open to 0.0.0.0/0
- HTTPS (Port 443) — Open to 0.0.0.0/0
- SSH (Port 22) — Open to 0.0.0.0/0

##  Project Structure

```
/var/www/html/
├── index.html           # Main portfolio page
├── contact.html         # Contact page
├── projects.html        # Projects showcase
├── resume.html          # Resume/CV
└── assets/
    ├── css/
    │   └── styles.css
    ├── js/
    │   └── scripts.js
    └── images/
```

## 🛠️ Common Commands

```bash
# Restart nginx
sudo systemctl restart nginx

# Reload configuration (without downtime)
sudo systemctl reload nginx

# Stop nginx
sudo systemctl stop nginx

# Start nginx
sudo systemctl start nginx

# Check error logs
sudo tail -f /var/log/nginx/error.log

# Check access logs
sudo tail -f /var/log/nginx/access.log
```

##  Server Status

| Component | Status |
|-----------|--------|
| Nginx |  Running |
| Port 80 |  Listening |
| Website | <img width="1895" height="952" alt="Screenshot 2026-06-25 173032" src="https://github.com/user-attachments/assets/a6de8d1f-a5eb-4583-ae1f-b3a4fe519e55" />
<img width="1553" height="327" alt="Screenshot 2026-06-25 003150" src="https://github.com/user-attachments/assets/2a18ff83-bc01-4bda-8450-48ec01de00a5" />
<img width="1567" height="707" alt="Screenshot 2026-06-25 003104" src="https://github.com/user-attachments/assets/8d3336b1-0204-4859-bee6-ea9c28051d87" />
<img width="1007" height="712" alt="Screenshot 2026-06-25 003053" src="https://github.com/user-attachments/assets/2919c991-1423-470a-b517-f30cf111370d" />
<img width="1437" height="568" alt="Screenshot 2026-06-25 003008" src="https://github.com/user-attachments/assets/c7a56393-ce73-4323-b60e-64292be00443" />
<img width="1428" height="937" alt="Screenshot 2026-06-25 002955" src="https://github.com/user-attachments/assets/cfce9bd3-b5e4-4b16-abe8-2e2309c2c8dc" />
<img width="1610" height="482" alt="Screenshot 2026-06-25 002944" src="https://github.com/user-attachments/assets/de8acded-7ea3-4f52-a155-d8a73b516b78" />
<img width="1168" height="432" alt="Screenshot 2026-06-25 002905" src="https://github.com/user-attachments/assets/8a7d5101-3a15-4e51-85e1-f4a8a63bf5a3" />
<img width="587" height="461" alt="Screenshot 2026-06-25 002854" src="https://github.com/user-attachments/assets/e4dfa4f3-f3ed-4bf2-8443-05291f1fb2ee" />
<img width="1900" height="961" alt="Screenshot 2026-06-25 002833" src="https://github.com/user-attachments/assets/2d25efab-f88e-4a6e-a49c-c567b1e8bbdd" />
<img width="1897" height="962" alt="Screenshot 2026-06-25 002816" src="https://github.com/user-attachments/assets/cc0318ac-2969-48b0-8c67-1dd702665d21" />
<img width="1863" height="403" alt="Screenshot 2026-06-25 001604" src="https://github.com/user-attachments/assets/2df9e773-df30-472b-b7e8-3ef670dcb422" />
<img width="1007" height="712" alt="Screenshot 2026-06-25 003053 - Copy" src="https://github.com/user-attachments/assets/e01a0a0b-7a8f-4848-923b-451e25d08f1b" />
 Live |
| Memory Usage | 3M |
| CPU Usage | Low |

##  Website Template

This deployment uses the **StartBootstrap Personal Portfolio Template** — a responsive Bootstrap 5 template perfect for showcasing projects and skills.

##  Troubleshooting

**Can't connect to website?**
- Verify security group allows port 80
- Check nginx is running: `sudo systemctl status nginx`
- Test locally first: `curl localhost`

**Nginx not starting?**
- Check configuration: `sudo nginx -t`
- Review error log: `sudo tail /var/log/nginx/error.log`

##  Next Steps

-  Add HTTPS/SSL certificate (Let's Encrypt)
   Configure custom domain name
  Set up auto-deployments with CI/CD
-  Enable CloudWatch monitoring
  Add CloudFront CDN for faster delivery

## Resources


- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [StartBootstrap Templates](https://startbootstrap.com/)

---

**Deployed:** June 24-25, 2026  
**Instance:** Running & Stable  
**Access:** http://13.41.109.132
