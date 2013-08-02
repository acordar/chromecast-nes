chromecast-nes
==============

A "Gaikai style" NES emulator for the chromecast<br>

Credit to NES Emulator here: https://github.com/bfirsh/jsnes

Credit to Homebrew Rom here: http://www.mojontwins.com/juegos_mojonos/sir-ababol-nes/

What is this?
--------------
This is a NES emulator "running" on a chromecast. What differeniates this from the Gameboy on the chromecast is that the NES emulator is
actually running on your sender device, i.e. your PC. In addition to running the emulator, your PC also sends the image of the emulator to the chromecast.
This, in effect, makes it a "Gaikai" or "OnLive" style of running the software sense all of the major processing is offloaded to your PC and the chromecast
just worries about displaying the image. 

What else does this mean?
--------------
This also means that any local ROM can be streamed to your chromecast. No more relying on the "cloud" 

Instructions
--------------
1) whitelist your device: https://developers.google.com/cast/whitelisting

2) Edit line 15 of receiver/index.html with your own APP ID

3) Edit line 39 of sender/index.html with your own APP ID

4) Put the receiver code at the URL you used to whitelist your chromecast

5) Put the sender code anywhere and tell your chromecast chrome extension to load the SDK at that domain (https://developers.google.com/cast/whitelisting)

6) Open the sender page in your browser... it should automatically connect to your chromecast and load the reciever page on your chromecast

7) Debug with following instructions https://developers.google.com/cast/developing_your_receiver#debugging

8) Add ROMs to the roms folder, and populate list on line 50 with whatever ROMs you have.

Tweak Settings
--------------
In sender/js/jsnes.js. There are two variables on lines 6889 and 6890 that can be used to adjust the quality and performance of the emulator.
frameNum tells how many frames to skip before rendering the next frame. Quality is the image quality that gets sent over to the chromecast.
