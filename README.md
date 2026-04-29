# AWS Deployment Test App (Task Manager)

A simple Node.js application designed to simulate and test deployments on various AWS services. It includes a basic task manager to verify interactive functionality after deployment.

## Features
- **Node.js + Express**: Standard backend for easy AWS compatibility.
- **Interactive UI**: Simple task management (add/delete tasks).
- **Responsive Design**: Works on mobile and desktop browsers.

---

## Local Development

1.  **Install dependencies:**
    ```bash
    npm install
    ```

2.  **Start the application:**
    ```bash
    npm start
    ```

3.  **View the app:**
    Open [http://localhost:8080](http://localhost:8080) in your browser.

---

## Lab Task: AWS Deployment Instructions

Follow these steps based on your chosen AWS service:

### 1. AWS Amplify (Frontend/Fullstack)
- **Best for:** Rapid deployment directly from Git.
- **Steps:**
    1. Push this code to a Git repository (GitHub, GitLab, or Bitbucket).
    2. In the AWS Amplify Console, click **"New App"** > **"Host web app"**.
    3. Connect your repository and select the branch.
    4. Amplify will automatically detect the build settings. Ensure the "Build command" is `npm install` and the "Start command" is `npm start`.
    5. Deploy and wait for the URL.

### 2. AWS Elastic Beanstalk (PaaS)
- **Best for:** Automated environment management.
- **Steps:**
    1. Create a ZIP file containing `server.js`, `package.json`, and the `public/` folder (do **not** include `node_modules`).
    2. Go to the Elastic Beanstalk console and click **"Create Application"**.
    3. Choose **Node.js** as the platform.
    4. Select **"Upload your code"** and upload your ZIP file.
    5. Once the environment is "Green", click the URL to test.

### 3. Amazon EC2 or Lightsail (IaaS/VPS)
- **Best for:** Full control over the server.
- **Steps:**
    1. Launch a Linux instance (e.g., Amazon Linux 2023 or Ubuntu).
    2. Security Group: Ensure **Port 80** (HTTP) and **Port 22** (SSH) are open.
    3. SSH into your instance.
    4. Install Node.js:
       ```bash
       curl -fsSL https://rpm.nodesource.com/setup_20.x | sudo bash -
       sudo yum install -y nodejs
       ```
    5. Clone or upload your code to the server.
    6. Run `npm install`.
    7. Start the app (use `sudo PORT=80 node server.js` to run on port 80).
    8. Visit the Instance Public IP in your browser.

---

## Project Structure
- `server.js`: Main Express server logic.
- `public/`: Contains the frontend (`index.html`).
- `package.json`: Dependencies and start scripts.
- `.gitignore`: Files to exclude from Git/Uploads.
