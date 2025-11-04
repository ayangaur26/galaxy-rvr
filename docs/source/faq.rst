.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

FAQ
==============

.. _install_lib:

1. Compilation error: ``SoftPWM.h`` or ``SunFounder_AI_Camera.h``: No such file or directory？
-------------------------------------------------------------------------------------------------
If you get a “Compilation error: ``SoftPWM.h``: No such file or directory” prompt, it means you don’t have the SoftPWM library installed.

Please install the two required libraries ``SoftPWM`` and ``SunFounder AI Camera`` as shown.

    .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/install_softpwm.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

For the ``SunFounder AI Camera`` library, you need to select "INSTALL ALL" to simultaneously install the required ``ArduinoJson`` dependency.

    .. image:: img/faq_install_ai_camera.png

2. avrdude: stk500_getsync() attempt 10 of 10: not in sync: resp=0x6e?
-----------------------------------------------------------------------------
If the following message keeps appearing after clicking the **Upload** button when the board and port have been selected correctly.

.. code-block::
    
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 2 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 3 of 10: not in sync: resp=0x00
    At this point, you need to make sure that the ESP32 CAM is unplugged.

The ESP32-CAM and the Arduino board share the same RX (receive) and TX (transmit) pins. So, before you’re uploading code, you’ll need to first disconnect the ESP32-CAM to avoid any conflicts or potential issues.

    .. image:: img/camera_upload.png
        :width: 500
        :align: center

After the code is successfully uploaded, if you need to use the ESP32 CAM, then you need to move the switch to the left to start the ESP32 CAM.

    .. image:: img/camera_run.png
        :width: 500
        :align: center

3. How to Change Wi-Fi Channel?
----------------------------------

The 2.4GHz Wi-Fi band has channels ranging from 1 to 13. ESP32 supports channels 1 to 11. Other devices operating on the same channel may cause interference, leading to connection issues. To mitigate this, you can try changing the channel. By default, the channel is set to 1. When selecting a new channel, it’s recommended to skip 1-2 channels at a time. For example, if the current channel is 1, try channel 3 first, and if the signal is still poor, proceed to channel 5.

.. note::

   ESP32 CAM firmware version 1.4.1 or above is required to change channels. Refer to :ref:`update_firmware` for more details.

#. Power on the GalaxyRVR. To activate the ESP32 CAM, move the mode switch to the **Run** position, and press the **reset** button to reboot the R3 board.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Find ``GalaxyRVR`` on the list of available networks on your mobile device (tablet or smartphone), enter the password ``12345678``, and connect to it.

     .. note::

        * The current connection is to the GalaxyRVR hotspot, so there is no internet access. If prompted to switch networks, please choose "Stay connected".
        * :ref:`ap_to_sta`

     .. image:: img/camera_lan.png
        :width: 500

#. Open a web browser on your mobile device and navigate to ``http://192.168.4.1`` to access the ESP32 CAM OTA update page.

   .. image:: img/faq_cam_ota_141.jpg
      :width: 400

#. Under the **Wi-Fi AP Channel** section, select a different channel. 

   * The default channel is 1. When selecting a new channel, skip 1-2 channels at a time (e.g., from channel 1 to 3, and if needed, to 5).  
   * Click the **Confirm** button to save the changes.

   .. image:: img/faq_cam_ota_channel.png
      :width: 400

#. A confirmation popup will appear, prompting you to reset the device. Click **Confirm**.

   .. image:: img/faq_cam_ota_reset.jpg
      :width: 400
   
#. Press the **Reset** button to reboot the device. The GalaxyRVR is now ready for normal operation.

   .. image:: img/camera_reset.png

.. _update_firmware:

4. How to Update Firmware for ESP32 CAM
-----------------------------------------

详细教程请参考：:ref:`update_firmware`

.. _restore_r3_firmware:

5. Restoring the R3 Board Default Firmware
-----------------------------------------------

The GalaxyRVR's R3 board comes preloaded with communication firmware that enables connectivity with both the RoboPilot remote control APP and Mammoth Coding software. If your board's firmware has been overwritten and you need to restore this communication capability, follow these steps to re-upload the firmware.

#. Turn on the GalaxyRVR's power switch.

   .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="../_static/video/play_start.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Connect the Arduino and computer with a USB cable, and then turn the **upload** switch of the car to the upload end.

   .. image:: img/camera_upload.png
        :width: 500
        :align: center

   .. note:: It is the USB Type B port for connecting to Arduino, not the USB Type C port for charging.

#. Check if you have completed :ref:`update_firmware` section.

#. Open the downloaded ``galaxy-rvr-1.2.0 folder``. (It has been downloaded and installed in the previous step), double-click to run the ``update-arduino-firmware.bat`` script. A command prompt will open.

   .. image:: img/firmware/updateFirmware.png

#. In the command prompt, you will see a serial port list showing the serial ports that the computer is currently connected to. Enter the sequence number on the left side of the serial port list to select the serial port of the Arduino Uno. Press Enter to automatically upload.

   .. image:: img/firmware/selectCOM.png

#. After waiting for the upload to complete, you can unplug the USB cable.

   .. image:: img/firmware/UNOupdating.png

.. note:: This code enables the GalaxyRVR to respond to APP commands. You won’t need to upload any more code in the subsequent chapters that use the APP.


.. _ap_to_sta:

Rover Network Configuration: Home WiFi and AP Mode
-----------------------------------------------------



How to Invert the Camera?  
---------------------------




About the ESP32 CAM Firmware
---------------------------------------------------

Here is the firmeware link of ESP32 CAM: |link_ai_camera_firmware|
