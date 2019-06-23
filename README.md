# PS/2 Mouse to CDi adapter

## The backstory

I bought an old Philips CDi off ebay, but it has been hard to find affordable input devices for it. I eventually built a SNEStoCDi to allow using SNES controllers, which works great, but I still wanted a mouse, so I hacked this project together to allow a PS2 mouse to be used with with a CDi.

I started from the [SNEStoCDi](https://github.com/anarterb/SNEStoCDi) project. To add PS/2 Mouse support, I grabbed the [PS2-Mouse-Arduino](https://github.com/kristopher/PS2-Mouse-Arduino) library, which needed a quick header fix to build on the lastest Arduino Software (1.6.12). My fork with the fix is [here](https://github.com/danbrakeley/PS2-Mouse-Arduino).

## Tech docs

To learn about the PS2 data protocol, I used Adam Chapweske's ["The PS/2 Mouse Interface"](http://www.computer-engineering.org/ps2mouse/).

To learn about the various CDi device protocols, I used some scans of Philips technical docs, which are included in [Paul Hackmann's CDi gamepad adapter source](https://web.archive.org/web/20121220052742/http://www.alpinecom.net/phackmann/cdiadapter/CDiGamepadAdapter.zip). 

## Install and build

First you need to add the PS2-Mouse-Arduino library. You can just clone [my PS2-Mouse-Arduino fork](https://github.com/danbrakeley/PS2-Mouse-Arduino) into your library folder. For Windows, that would be `C:\Users\<username>\Documents\Arduino\libraries\`.

Next you need to clone this project down somewhere, and then just open the `.ino` file in the sketch folder, set the pin constants at the top of the source to the pins you plan on using, and compile and go.

If you want to test out your PS/2 Mouse, you can disable the CDi stuff by setting `ENABLE_CDI` to `false`, then enabling the serial prints I put in there by setting `DEBUG_OUT_ENABLED` to `true`.
