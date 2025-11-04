
.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

.. _update_firmware:

Updating the ESP32 Firmware
==============================

Your device may not have the latest firmware due to product iterations. To ensure stable performance, follow the steps below to check and update the firmware on your ESP32.

#. Start the GalaxyRVR.

   * When using GalaxyRVR for the first time, it is recommended to fully charge the battery by plugging in a Type-C USB cable. Then, turn on the power.
    
     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_start.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

   * To activate the ESP32 CAM, switch the mode to **Run** and press the **reset** button to reboot the R3 board. You will see the light on the bottom strip start flashing, indicating that the device has started.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Download the firmware file.

   * :download:`GalaxyRVR Firmware File <https://github.com/sunfounder/galaxy-rvr/releases/download/1.2.0/galaxy-rvr-1.2.0.zip>`

#. Extract the downloaded file and transfer the file ``ai-camera-firware.ino.x.x.x.bin`` to your mobile device. You can use any file transfer app, such as ES File Explorer or File Transfer Assistant.

   .. image:: img/firmware/selectBin.png
        :width: 400px
        :align: center

#. Connect your mobile device to the GalaxyRVR WiFi hotspot.

   * The default SSID is ``GalaxyRVR`` and the password is ``12345678``.  
   * If a warning appears about no internet access, select **“Stay connected”**.


   .. image:: img/firmware/SSID.png
        :width: 400px
        :align: center
       
#. On your mobile device, open a browser and navigate to ``http://192.168.4.1`` to access the ESP32 Cam firmware update page.

   .. image:: img/firmware/OTAUpdate.jpg
        :width: 400px
        :align: center

#. Check the firmware version. 

   * If your version number is higher than ``1.5.1``, no update is required (you can skip the following steps).  
   * If it is lower, proceed with the upgrade.

   .. image:: img/firmware/OTAversion.jpg
        :width: 400px
        :align: center

#. Return to the update interface and click the button to select the firmware.

   .. image:: img/firmware/OTASButton.jpg
        :width: 400px
        :align: center

#. Select the ``ai-camera-firware.ino.x.x.x.bin`` file that you previously stored on your mobile device, then click **Upgrade**.

   .. image:: img/firmware/OTASelect.jpg
        :width: 400px
        :align: center

#. Wait for the firmware upgrade to complete. 

   * Once the version number shows ``x.x.x``, the update is successful.  
   * You can now close this page and move on to the next chapter.

   .. image:: img/firmware/OTAFinish.jpg
        :width: 400px
        :align: center

