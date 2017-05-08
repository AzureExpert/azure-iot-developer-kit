---
title: "Getting Started Guide"
permalink: /docs/getting-started/
excerpt: "How to quickly install and setup development environment for use with DevKit."
last_modified_at: 2016-04-30T10:01:43-04:00
---

For a first-time user of the MXChip IoT Developer Kit (a.k.a DevKit), follow these quick steps to prepare your development environment and begin building IoT applications.

## Step 1. Before starting

### What you need

* MXChip IoT Developer Kit. [Get it now](http://microsoft.github.io/azure-iot-developer-kit){:target="_blank"}
* A computer running Windows 10 (64-bits) or macOS 10.10+ (coming soon)
* An active Azure subscription
  * Activate a [free 30-day trial Microsoft Azure account](https://azureinfo.microsoft.com/us-freetrial.html){:target="_blank"}

### Download the latest package

The `.zip` file you download contains all necessary tools and packages required for DevKit development.

[<i class='fa fa-download'></i> Download](https://azureboard.blob.core.windows.net/installpackage/usb_install_latest.zip){: .btn .btn--success .btn--large}

**Note:** If you are using the old version of the DevKit, download [legacy build](https://azureboard.blob.core.windows.net/installpackage/usb_install_legacy.zip).
{: .notice--info}

> The `.zip` file contains the following tools and packageas. If you already have some components installed, the script will detect and skip them.
> * Node.js and Yarn: Runtime for the setup script and automated tasks
> * Python and pip: For running Azure CLI 2.0
> * [Azure CLI 2.0](https://docs.microsoft.com/en-us/cli/azure/overview){:target="_blank"} - Cross-platform  command-line experience for managing Azure resources
> * [Visual Studio Code](https://code.visualstudio.com/){:target="_blank"} (VS Code): Lightweight code editor for DevKit development
> * [VS Code Arduino Extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.vscode-arduino){:target="_blank"}: Enables Arduino development in VS Code
> * [Arduino IDE](https://www.arduino.cc/en/Main/Software){:target="_blank"}: VS Code Arduino Extension relies on this tool
> * DevKit Board Package: Toolchains, libraries and projects for the DevKit
> * ST-Link Utility: Essential utility and drivers

**VS Code Arduino Extension**: The DevKit currently is using a special version of Arduino extension for VS Code. If you have notification for update the extension, please just ignore it. If you accidentally updated it, follow these [manual steps]({{"docs/faq/#after-updateing-arduino-extension-in-vs-code-it-breaks-everything" | absolute_url}}) to bring it back to work.
{: .notice--warning}

## Step 2. Set up the development environment

Run the script to automatically install tools and packages.

### A. Run installation script

In the File Explorer, locate the `.zip` and extract it, find `azure-install.cmd`, right-click and select **"Run as administrator"** to start.

![getting-started-run-admin]({{"/assets/images/getting-started-run-admin.png" | absolute_url }})

During installation, you will see the progress of each tool or package.

![getting-started-install]({{"/assets/images/getting-started-install.png" | absolute_url }})

### B. Confirm to install drivers

The VS Code for Arduino extension relies on the Arduino IDE to work. If this is the first time you are installing Arduino IDE, you will be prompted to install relevant drivers:

![getting-started-driver]({{"/assets/images/getting-started-driver.png" | absolute_url }})

It should take 10 minutes to finish all installations depending on your Internet speed. Once installation is complete, you should see Visual Studio Code and Arduino IDE shortcuts on your desktop.

## Step 3. Prepare your hardware

Hook up your hardware to your computer.

### A. What you need

* DevKit board
* Micro USB cable

![getting-started-hardware]({{"/assets/images/getting-started-hardware.jpg" | absolute_url }})

### B. Launch VS Code

This will be the primary editor for DevKit development. Be sure to open VS Code before connecting to the DevKit so that it can automatically detect the board.

### C. Connect DevKit to your computer via USB

![getting-started-connect]({{"/assets/images/getting-started-connect.jpg" | absolute_url }})

1. Connect USB end to your PC
2. Connect Micro USB end to the DevKit
3. The green LED next to power confirms connection

VS Code will detect DevKit and automatically display an introduction page with examples next to it:

![getting-started-vscode]({{"/assets/images/getting-started-vscode.png" | absolute_url }})

## Step 4. Configure WiFi



## Next Steps

You are all set! It's time to build your first IoT application by following instructions in [Projects Catalog]({{"/docs/projects/" | absolute_url }}).
