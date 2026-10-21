# Lab 5: Machine Learning + Biomimicry

## Overview

Create an interactive website using TensorFlow.js and Teachable Machine. Choose between training a model with images, sound, or body poses, and use biomimicry to guide the interaction. Then create a cybernetic loop diagram that explains how input, output, and feedback connect.

### Use Biomimicry to Guide Your Design

Choose a biological behavior or process and translate it into an interaction. For example, train an image model to distinguish light and dark images. When the model detects light, a plant grows onscreen. When it detects darkness, growth pauses.

## 1. Review the Resources

Review the [resources below](#resources) related to biomimicry and machine learning.

## 2. Set Up

- Install [Visual Studio Code](https://code.visualstudio.com/) and the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).
- Install the Codex extension in VS Code and sign in with your Duke ChatGPT account. Follow the [Duke ChatGPT Edu instructions](https://oit.duke.edu/service/chatgpt-edu/) to activate your access.
- **Windows users:** Follow the [VS Code WSL guide](https://code.visualstudio.com/docs/remote/wsl) to install WSL and the WSL extension. Open your project in WSL and install Live Server there when prompted.
- Create a project folder and open it in VS Code.

## 3. Train a Model

1. Open [Teachable Machine](https://teachablemachine.withgoogle.com/) and choose an image, audio, or pose project.
2. Create classes for the inputs you want to recognize, such as **light** and **dark**. Record examples for each class.
3. Train the model and try new inputs. Add more training data if it makes mistakes.
4. Choose **Export Model → TensorFlow.js**. Save the model files or hosted model URL and copy the example code.

## 4. Build and Test

1. Use the exported example code to connect your model to your website.
2. Make the predictions change something onscreen. Use a behavior from nature to guide the response.
3. In VS Code, right-click `index.html` and choose **Open with Live Server**, or click **Go Live** near the bottom-right corner.
4. Allow camera or microphone access and test your interaction. Use the `localhost` address in your browser.
5. Save your website in a Git repository and push it to GitHub. Include any model files you use, or the hosted model URL, and a short README explaining how to run it.

## 5. Draw the Cybernetic Loop

Create a cybernetic loop diagram that explains how input, output, and feedback connect. Draw your diagram by hand or use [Excalidraw](https://excalidraw.com/). Save it as an image or PDF.

## 6. Deploy with Dokploy

In your [Dokploy](https://dokploy.com/) dashboard:

1. Create a project and add an **Application**.
2. Connect your Git repository and select the branch to deploy.
3. Choose **Static** as the build type and set the root directory to the folder containing `index.html`.
4. Click **Deploy**.
5. Add a domain using port **80** and enable **HTTPS** so camera or microphone access works.
6. Open the public URL and test the interaction.

See the [Dokploy static HTML guide](https://docs.dokploy.com/docs/core/html) for reference.

## Submit to Canvas

Submit three items:

- **Git repository link** with your website code and model files or model URL.
- **Live static website link**, deployed through Dokploy.
- **Cybernetic loop diagram** as an image or PDF.

## Resources

### Biomimicry Readings and Viewing

- **[Video]** Janine Benyus, [“Biomimicry in Action”](https://www.ted.com/talks/janine_benyus_biomimicry_in_action).
- **[Reading]** Smithsonian Magazine, [“How Biomimicry is Inspiring Human Innovation”](https://www.smithsonianmag.com/science-nature/how-biomimicry-is-inspiring-human-innovation-17924040/).

### Teachable Machine

- [Teachable Machine v2](https://teachablemachine.withgoogle.com/) — use this for the workshop.
- [Teachable Machine v1](https://teachablemachine.withgoogle.com/v1/) — earlier version, included for reference.
- [Official Teachable Machine libraries and examples](https://github.com/googlecreativelab/teachablemachine-community).

### Neural Networks

- [ml5.js Neural Network Reference](https://docs.ml5js.org/#/reference/neural-network).
- [GeeksforGeeks: Neural Networks — A Beginner’s Guide](https://www.geeksforgeeks.org/deep-learning/neural-networks-a-beginners-guide/).
- [IBM: What Are Neural Networks?](https://www.ibm.com/think/topics/neural-networks).
- [Neural Networks — Video Resource](https://www.youtube.com/watch?v=jmmW0F0biz0).

### Inspiration

- [TensorFlow.js Demos](https://www.tensorflow.org/js/demos).
- [Google Experiments: Teachable Machine](https://experiments.withgoogle.com/search?q=teachable%20machine).
