# PS5-Server32
 
This is a project designed for the <a href=https://www.espressif.com/en/products/socs/esp32-s2>ESP32-S2</a>, *<a href=https://www.espressif.com/en/products/socs/esp32-s3>ESP32-S3</a> and <a href=https://www.espressif.com/en/products/socs/esp32>ESP32</a> boards to provide a wifi http server, dns server and *<b>USB storage emulation</b>.

<br>


## Libraries

the project is built using <b><a href=https://github.com/fhessel/esp32_https_server>ESP32 HTTPS Server</a></b> so you need to add this library to arduino.

<a href=https://github.com/fhessel/esp32_https_server>ESP32 HTTPS Server</a><br>

<br>

install or update the ESP32 core by adding this url to the <a href=https://docs.arduino.cc/learn/starting-guide/cores>Additional Boards Manager URLs</a> section in the arduino "<b>Preferences</b>".

` https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json `

then goto the "<b>Boards Manager</b> and install or update the "<b>esp32</b>" core.

<br>

if you have problems with the board being identified/found in windows then you might need to install the <a href=https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers>USB to UART Bridge</a> drivers.


<br>


## Tested Boards

these <a href=https://www.espressif.com/en/products/socs/esp32-s2>ESP32-S2</a> boards can be used for a plug and play setup(no wiring)<br>
<br>
4MB boards<br>

:ok: <a href=https://www.wemos.cc/en/latest/s2/s2_mini.html>S2 Mini</a><br>
:ok: <a href=https://unexpectedmaker.com/tinys2>TinyS2</a><br>
:ok: <a href="https://www.adafruit.com/product/5325">Adafruit QT Py ESP32-S2</a><br>
:ok: <a href=https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/hw-reference/esp32s2/user-guide-s2-devkitc-1.html>ESP32-S2-DevKitC-1</a><br>
:ok: <a href="http://www.lilygo.cn/prod_view.aspx?TypeId=50063&Id=1320&FId=t3:50063:3">ESP32-S2 ESP32-S2-WOOR</a><br>
:ok: <a href="http://www.lilygo.cn/prod_view.aspx?TypeId=50063&Id=1300&FId=t3:50063:3">ESP32-S2 ESP32-S2 TF Card Slot</a><br>

16MB boards<br>
:ok: <a href=https://feathers2.io/>FeatherS2</a><br>

<br>

<hr>these <a href=https://www.espressif.com/en/products/socs/esp32-s2>ESP32-S2</a> boards will need a usb A plug wired up to them.<br>
<br>
4MB boards<br>

:ok: <a href=https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/hw-reference/esp32s2/user-guide-devkitm-1-v1.html>ESP32-S2-DevKitM-1</a> Wiring <a href=https://github.com/stooged/PS5-Server32/blob/main/Images/esp32-s2-devkitm-1.jpg>Diagram</a><br>
:ok: <a href=https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/hw-reference/esp32s2/user-guide-saola-1-v1.2.html>ESP32-S2-Saola-1</a> Wiring <a href=https://github.com/stooged/PS5-Server32/blob/main/Images/esp32-s2-saola-1.jpg>Diagram</a><br>
:ok: <a href=https://docs.ai-thinker.com/en/12k_development_board_esp32-s2>Ai-thinker ESP 12K</a> Wiring <a href=https://github.com/stooged/PS5-Server32/blob/main/Images/ai-thinker-esp12k.jpg>Diagram</a><br>

<br>
<hr>

these <a href=https://www.espressif.com/en/products/socs/esp32-s3>ESP32-S3</a> boards can be used for a plug and play setup(no wiring)<br>
note that the esp32-s3 boards are not yet officially supported by the esp32 library, the following boards work but require a <a href=https://github.com/espressif/arduino-esp32/tree/esp32-s3-support>development version of the esp32 library</a> installed.

:warning: <a href=https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1.html>ESP32-S3-DevKitC-1</a><br>

<br>


## Uploading to board

installation is simple you just use the arduino ide to flash the sketch/firmware to the esp32 board.<br>
<br>
next you connect to the wifi access point with a pc/laptop, <b>PS4_WEB_AP</b> is the default SSID and <b>password</b> is the default password.<br>
then use a webbrowser and goto http://10.1.1.1/admin.html <b>10.1.1.1</b> is the defult webserver ip or http://ps5.local<br>
on the side menu of the admin page select <b>File Uploader</b> and then click <b>Select Files</b> and locate the <b>data</b> folder inside the <b>PS5_Server32</b> folder in this repo and select all the files inside the <b>data</b> folder and click <b>Upload Files</b>
you can then goto <b>Config Editor</b> and change the password for the wifi ap.


alternatively if you install this <a href=https://github.com/stooged/arduino-esp32fs-plugin>plugin</a> to the arduino ide you can upload the files to the board storage with the arduino ide by selecting <b>Tools > ESP32 Sketch Data Upload</b>

<a href=https://github.com/stooged/arduino-esp32fs-plugin>Arduino ESP32-S2 filesystem uploader</a>

<img src=https://github.com/stooged/PS5-Server32/blob/main/Images/dataup.jpg><br><br>

the files uploaded using this method are found in the <b>data</b> folder inside the <b>PS5_Server32</b> folder.

<br>



## Internal pages

* <b>admin.html</b> - the main landing page for administration.

* <b>index.html</b> - if no index.html is found the server will generate a simple index page and list the payloads automatically.

* <b>info.html</b> - provides information about the esp board.

* <b>upload.html</b> - used to upload files(<b>.bin</b>) to the esp board for the webserver.

* <b>update.html</b> - used to update the firmware on the esp board (<b>fwupdate.bin</b>).

* <b>fileman.html</b> - used to <b>view</b> / <b>download</b> / <b>delete</b> files on the internal storage of the esp board.

* <b>config.html</b> - used to configure wifi ap and ip settings.

* <b>format.html</b> - used to format the internal storage of the esp board.

* <b>reboot.html</b> - used to reboot the esp board


<br><br>



## Cases

i have created some basic printable cases for the following boards.<br>
these cases can be printed in PLA without supports.

### ESP32-S2 Boards

<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/Adafruit_QT_Py>Adafruit QT Py</a><br>
<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/UM_FeatherS2>UM FeatherS2</a><br>
<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/UM_TinyS2>UM TinyS2</a><br>
<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/Wemos_S2_Mini>Wemos S2 Mini</a><br>
<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/DevKitM_1>DevKitM-1</a><br>
<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/ESP32_S2_Saola_1>ESP32-S2-Saola-1</a><br>


### ESP32-S3 Boards

<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/S3_DevKitC_1>S3_DevKitC_1</a><br>


### ESP32 Boards

<a href=https://github.com/stooged/PS5-Server32/tree/main/3D_Printed_Cases/NodeMCU_32>NodeMCU-32</a><br>

<br>

if you wish to edit the cases you can import the `.stl` files into <a href=https://www.tinkercad.com/>Tinkercad<a/> and edit them to suit your needs.

<br>