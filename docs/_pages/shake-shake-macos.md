---
title: "Shake, shake"
permalink: /docs/projects/shake-shake-macos/
---

**Note:** This manual steps for running **'Shake, shake'** project on macOS is subject to be changed.
{: .notice--warning}

### Step 1. Create Azure IoT Hub

1. Sign in to [Azure portal](https://portal.azure.com/).

2. Click **New > Internet of Things > IoT Hub**:
 ![shake-shake-mac-iothub]({{"/assets/images/shake-shake-mac-iothub.png" | absolute_url }})

3. In the **IoT hub** pane, enter the following information for your IoT hub:
 ![shake-shake-mac-hub-details]({{"/assets/images/shake-shake-mac-hub-details.png" | absolute_url }})
 > * **Name**: It is the name for your IoT hub. If the name you enter is valid, a green check mark appears.
 > * **Pricing and scale tier**: Select the free F1 tier. This option is sufficient for this demo. See [pricing and scale tier](https://azure.microsoft.com/pricing/details/iot-hub/){:target="_blank"}.
 > * **Resource group**: Create a resource group to host the IoT hub or use an existing one. See Using [resource groups to manage your Azure resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-portal){:target="_blank"}.
 > * **Location**: Select the closest location to you where the IoT hub is created.
 > * **Pin the dashboard**: Check this option for easy access to your IoT hub from the dashboard.

4. Click **Create**. It could take a few minutes for your IoT hub to be created. You can see progress in the **Notifications** pane:
 ![shake-shake-mac-notification]({{"/assets/images/shake-shake-mac-notification.png" | absolute_url }})

5. After your IoT hub is created, click it from the dashboard. Make a note of the **Hostname** value that is used later in this article, and then click **Shared access policies**:
 ![shake-shake-mac-policies]({{"/assets/images/shake-shake-mac-policies.png" | absolute_url }})

6. In the **Shared access policies** pane, click the **iothubowner** policy, and then copy and save the **Connection string** value for your IoT hub:

### Step 2. Register a device in the IoT hub for the your device

1. In the [Azure portal](https://portal.azure.com/){:target="_blank"}, open your IoT hub.

2. Click **Device Explorer**.

3. In the Device Explorer pane, click **Add** to add a device to your IoT hub:
 ![shake-shake-mac-device]({{"/assets/images/shake-shake-mac-device.png" | absolute_url }})
 > * **Device ID**: The ID of the new device.
 > * **Authentication type**: Select Symmetric Key.
 > * **Auto generate keys**: Check this field.
 > * **Connect device to IoT Hub**: Click Enable.

4. Click **Save**.

5. After the device is created, open the device in the **Device Explorer** pane.

6. Make a note of the primary key of the connection string.
 ![shake-shake-mac-connection-string]({{"/assets/images/shake-shake-mac-connection-string.png" | absolute_url }})

### Step 3. Configure device connection string to DevKit

1. With your DevKit connected to computer, open the terminal.

2. List relevant serial port:
 ```bash
 ls -l /dev/cu.*
 ```
 You get following outputs like:
 ```bash
 crw-rw-rw-  1 root  wheel   20,   1 May 17 18:36 /dev/cu.Bluetooth-Incoming-Port
 crw-rw-rw-  1 root  wheel   20,  33 May 18 18:11 /dev/cu.usbmodem1423
 ```
 The later one ended with `usbmodem1423` is the actual serial port of the DevKit.

3. Open serial monitor:
 ```bash
 screen /dev/cu.usbmodem1423 115200
 ```

4. Get into configuration mode:
 Hold down button A, click Reset button, then release button A.

5. In the prompt of the serial port with `#`, configure your connection string you get from previous step:
 ```bash
 set_az_iothub [your connection string]
 ```
 You will see the information once configuration is successful:
 ```bash
 INFO: Set Azure Iot hub connection string successfully.
 ```
 Now exit the serial monitor by first type `Ctrl+A` and then `Ctrl+\` and type 'y'.

### Step 4. Deploy Azure Functions

*TBD*

### Step 5. Build and upload Arduino sketch

#### A. Open Arduino Examples folder in VS Code:

Launch VS Code first and connect the DevKit to your computer. VS Code will automatically find it and pops up introduction page. Switch to **'Arduino Examples'** tab, navigate to `Examples for MXChip AZ3166 > AzureIoTHub` and click on `ShakeShake`.

![shake-shake-example]({{"/assets/images/shake-shake-example.png" | absolute_url }})

#### B. Compile and upload the Arduino sketch

Use `Ctrl+Shift+P` to invoke command palette and type **Arduino** then find and select **Arduino: Upload**. Then it will start compiling and uploading the Arduino sketch. After it is done, the DevKit will reboot and start running the code.

## Test the project

Check how to [test the result]({{"/docs/projects/shake-shake/#test-the-project" | absolute_url }}).