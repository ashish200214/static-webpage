
## CI/CD Workflow Using Jenkins and GitHub Webhooks

This project demonstrates a simple and practical CI/CD pipeline using **Jenkins**, **GitHub Webhooks**, and **Linux servers**.

### Architecture Overview

* **Jenkins Server**
  Used for automation, build, and deployment tasks.

* **Live Server (Web Server)**
  Hosts the actual website and serves the HTML files using a web server (Apache/Nginx).

* **GitHub Repository**
  Contains the website source code (`.html` files).

---

### Workflow Explanation

1. **Code Push to GitHub**
   Any change pushed to a specific branch in the GitHub repository triggers a webhook event.

2. **GitHub Webhook → Jenkins**
   The webhook notifies the Jenkins server whenever changes are made to the configured branch.

3. **Jenkins Job Execution**
   After receiving the webhook:

   * Jenkins clones the latest version of the repository.
   * The build process starts automatically.

4. **Build Step (Packaging)**

   * Jenkins searches for all files ending with `.html`.
   * These files are compressed into a single ZIP file.

5. **Transfer to Live Server**

   * Jenkins securely copies (`scp`) the ZIP file to the live server using SSH authentication.

6. **Deployment on Live Server**

   * Jenkins connects to the live server via SSH.
   * Existing files in `/var/www/html` are removed.
   * The ZIP file is extracted in `/var/www/html`.

7. **Website Update**

   * The live server immediately serves the updated HTML files.
   * No manual intervention is required.

---

### Key Features

* Automated deployment using **GitHub Webhooks**
* Secure file transfer using **SCP and SSH**
* Clean separation between **CI server** and **production server**
* Real-time website updates on every code push

---

### Use Case

This setup is ideal for:

* Static websites
* Learning CI/CD fundamentals
* Understanding real-world Jenkins automation
* Practicing server-to-server deployments

---

### Summary

This pipeline ensures that every change pushed to GitHub is automatically built and deployed to the live server, making the deployment process fast, consistent, and reliable.

---

If you want, I can:

* Convert this into a **diagram**
* Add **Jenkinsfile snippet**
* Make it more **casual** or more **enterprise-style**

Just tell me 👍
