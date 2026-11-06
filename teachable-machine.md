# Teachable Machine

## Overview

Create an interactive website using TensorFlow.js and Teachable Machine. Train a model with images, sound, or body poses, use its predictions to change something onscreen, and deploy your website with Dokploy.

## 1. Set Up

- Install [Visual Studio Code](https://code.visualstudio.com/) and the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).
- Install the Codex extension in VS Code and sign in with your Duke ChatGPT account. Follow the [Duke ChatGPT Edu instructions](https://oit.duke.edu/service/chatgpt-edu/) to activate your access.
- **Windows users:** Follow the [VS Code WSL guide](https://code.visualstudio.com/docs/remote/wsl) to install WSL and the WSL extension. Open your project in WSL and install Live Server there when prompted.
- Create a project folder and open it in VS Code.

## 2. Train a Model

1. Open [Teachable Machine](https://teachablemachine.withgoogle.com/) and choose an image, audio, or pose project.
2. Create classes for the inputs you want to recognize, such as different objects, sounds, or poses. Record examples for each class.
3. Train the model and try new inputs. Add more training data if it makes mistakes.
4. Choose **Export Model → TensorFlow.js**. Save the model files or hosted model URL and copy the example code.

## 3. Build and Test

1. Use the exported example code to connect your model to your website.
2. Make the predictions change something onscreen. For example, use different poses to change colors, switch scenes, or control an animation.
3. In VS Code, right-click `index.html` and choose **Open with Live Server**, or click **Go Live** near the bottom-right corner.
4. Allow camera or microphone access and test your interaction. Use the `localhost` address in your browser.
5. Save your website in a Git repository and push it to GitHub. **Make sure your Git repository is public.** Include any model files you use, or the hosted model URL, and a short README explaining how to run it.

## 4. Set Up Dokploy

If you already have a working Dokploy dashboard, continue to **Deploy Your Website** below.

1. Spin up a virtual machine (VM) using [Virtual Computing Manager](https://vcm.duke.edu/).
2. Click **Request a VM**, select **Linux**, and choose **Ubuntu Server 24.04**.
3. Create an alias, such as `[first name]-teachable-machine`.
4. Turn off **Automatic power downs** and provide a reason, such as "Deploying an interactive website for a class."
5. SSH into the machine using the admin user and the VM's **hostname** shown in Virtual Computing Manager. Replace `admin` with your admin username and `your-vm-hostname` with the full hostname:

   ```sh
   ssh admin@your-vm-hostname
   ```

   Enter your password when prompted.

6. Start a root login shell before installing Dokploy:

   ```sh
   sudo -i
   ```

   Then install Dokploy:

   ```sh
   curl -sSL https://dokploy.com/install.sh | sh
   ```

7. Open the dashboard address shown by the installer. Create a username and password and store them safely.
8. In the Dokploy dashboard, go to **Settings** and enter your alias in the **Domain** field, such as `your-alias.colab.duke.edu`.
9. Enter your email in the **Let's Encrypt Email** field, turn **HTTPS** on, and select **Let's Encrypt** from the **Certificate Provider** dropdown.

## 5. Deploy Your Website

In your [Dokploy](https://dokploy.com/) dashboard:

1. Go to **Projects**, click **Create Project**, and select **Create Service → Application**.
2. Choose how to provide your website files:
   - **Git repository:** Connect your Git repository and select the branch to deploy.
   - **ZIP upload:** Under **General**, click **Drop**. Zip your static website files and upload the ZIP. Include `index.html`, scripts, styles, assets, and any locally saved model files.
3. Under **Build Type**, choose **Static**. Set the root directory to the folder containing `index.html`, then click **Save**.
4. Click **Deploy**.
5. Under **Domains**, click **Add Domain**. Click the dice icon to generate a random domain. Set **Container Port** to `80`, turn **HTTPS** on, select **Let's Encrypt** as the **Certificate Provider**, and click **Create**.
6. Open the public **HTTPS** URL, allow camera or microphone access, and test the interaction. Check that your model loads and the website responds to each class.

The dashboard domain and the application's domain are configured separately. Enable HTTPS for the application so camera or microphone access works on the public website.

See the [Dokploy static HTML guide](https://docs.dokploy.com/docs/core/html) for reference.

## Submit to Canvas

Submit two items:

- **Git repository link** with your website code and model files or model URL.
- **Live static website link**, deployed through Dokploy.

## Follow-Up: Connect Your Model to TouchDesigner

Connect your Teachable Machine model to TouchDesigner using [this tutorial](https://derivative.ca/community-post/tutorial/easily-train-pose-image-audio-detection-ai-touchdesigner-no-code-teachable).

## Resources

- [Teachable Machine](https://teachablemachine.withgoogle.com/).
- [Official Teachable Machine libraries and examples](https://github.com/googlecreativelab/teachablemachine-community).
- [TensorFlow.js Demos](https://www.tensorflow.org/js/demos).
- [ml5.js](https://ml5js.org/).
- [IBM: What Are Neural Networks?](https://www.ibm.com/think/topics/neural-networks).
- [Dokploy static HTML guide](https://docs.dokploy.com/docs/core/html).
