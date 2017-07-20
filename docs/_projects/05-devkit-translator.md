---
title: "DevKit Translator"
permalink: /docs/projects/devkit-translator/
excerpt: "Use the devkit and azure services to achieve speech translation."
header:
  image: 
  teaser: 
layouts_gallery:
  - url: /assets/images/mini-solution-devkit-translator-1.jpg
    image_path: /assets/images/mini-solution-devkit-translator-1.jpg
    alt: "Arduino application initializing"
  - url: /assets/images/mini-solution-devkit-translator-2.jpg
    image_path: /assets/images/mini-solution-devkit-translator-2.jpg
    alt: "DevKit Initialized"
  - url: /assets/images/mini-solution-devkit-translator-3.jpg
    image_path: /assets/images/mini-solution-devkit-translator-3.jpg
    alt: "Choose source language-1"
  - url: /assets/images/mini-solution-devkit-translator-4.jpg
    image_path: /assets/images/mini-solution-devkit-translator-4.jpg
    alt: "Choose source language-2"
  - url: /assets/images/mini-solution-devkit-translator-5.jpg
    image_path: /assets/images/mini-solution-devkit-translator-5.jpg
    alt:  "Ready to talk"
  - url: /assets/images/mini-solution-devkit-translator-6.jpg
    image_path: /assets/images/mini-solution-devkit-translator-6.jpg
    alt:  "Translation"
variable:
  - platform: windows
    name: Windows
last_modified_at: 2017-07-17T20:15:34-04:00
---

In this project, you will learn how to use the the devkit as a translator. The app will record your voice and translate it to English text show in the screen.

{% include toc icon="columns" %}

## What you need

* Finish the [Getting Started Guide]({{"/docs/get-started/" | absolute_url }})

{% include switch.html content = page.variable %}

## Windows

### Step 1. Open project folder

#### A. Launch VS Code

Make sure your DevKit is not connected. Launch VS Code first and connect the DevKit to your computer. VS Code will automatically find it and pop up an introduction page:

![mini-solution-vscode]({{"/assets/images/mini-solution-vscode.png" | absolute_url }})

**Notice:** Occasionally, when you launch VS Code, you will be prompted with error that cannot find Arduino IDE or related board package. To solve it, close VS Code, launch Arduino IDE once again and VS Code should locate Arduino IDE path correctly.
{: .notice--warning}

#### B. Open Arduino Examples folder

Switch to **'Arduino Examples'** tab, navigate to `Examples for MXCHIP AZ3166 > AzureIoT` and click on `DevKitTranslator`.

![mini-solution-catalog]({{"/assets/images/mini-solution-catalog-devkit-translator.png" | absolute_url }})

If you happen to close the **Arduino Examples** pane, to reload it, use `Ctrl+Shift+P` to invoke command palette and type **Arduino** to find and select **Arduino: Examples**.

### Step 2. Provision Azure services

In the solution window, run your task through **Quick Open** (`Ctrl+P`) by typing 'task cloud-provision':

In the VS Code terminal, an interactive command line will guide you through provisioning all required Azure services:

![mini-solution-provision-sub]({{"/assets/images/mini-solution-provision-sub-devkit-translator.png" | absolute_url }})

### Step 3. Deploy Azure Functions

Use **Quick Open** (`Ctrl+P`) to run 'task cloud-deploy' to deploy the Azure Functions code. It usually take 2 to 5 minutes to complete:

![mini-solution-deploy]({{"/assets/images/mini-solution-deploy-devkit-translator.png" | absolute_url }})

### Step 4. Build and upload Arduino sketch

Use **Quick Open** (`Ctrl+P`) to run 'task device-upload'. The terminal will prompt you to enter configuration mode: hold down button A, then push and release the reset button. The screen will display 'Configuration'. This step is to set the connection string which is retrieved from 'task cloud-provision'.

After that it will start verifying and uploading the Arduino sketch:

![mini-solution-build]({{"/assets/images/mini-solution-build-devkit-translator.png" | absolute_url }})

The DevKit will reboot and start running.

**Notice:** If you are running on a clean machine with everything installed, during the verifying of the code phrase, you might get an error of **Unknown board AZ3166**.
To work around, open Arduino IDE, navigate to **Tool > Board manager**. Arduino will reload all json files of all package definitions. After that, launch VS Code and try to build again, everything will be good.
{: .notice--warning}

## Test the project

After app initialization, follow the instructions in the screen to setup. You could just press button B to talk. The default language is Chinese. Or, you may press button A to enter setup mode. Press button B to scroll all supported languages, then press button A to confirm your choice. After source language is set, press button B to talk and release to send the voice. Several seconds later, the translation will be showed in the screen.

{% include gallery id="layouts_gallery" caption="Translate as you go" %}

- Press button A and B to scroll and select source language
- Press button B to talk, release to send the void and get the translation text

**Note:** If the devkit stay long in 'Receiving...' status on screen without getting the results. You could try to press `Reset` button to restart the app.
{: .notice--info}

## How it works

![mini-solution-voice-to-tweet-diagram]({{"/assets/images/mini-solution-diagram-devkit-translator.png" | absolute_url }})

The Arduino sketch records your voice, post a http request to trigger Azure Functions. Azure Functions calls the cognitive service speech translator api to do the translation. After azure function gets the translation text, it sends a C2D message to the device. Then the translation shows in the screen.

## Feedback

You can find [FAQs]({{"/docs/faq/" | absolute_url }}) if you encounter other problems or reach out to us from the channels below.