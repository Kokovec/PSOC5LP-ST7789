# PSOC5LP-ST7789
Example of a PSOC5LP controlling an ST7789 driven display

This is a PSOC5LP firmware example to control an ST7789 LCD controller.
This is orgiinally built for th Infinion CY8CKIT-059 (https://www.mouser.com/ProductDetail/Infineon-Technologies/CY8CKIT-059?qs=PhR8RmCirEblciDRmpiVDw%3D%3D)
The LCD display used: IPS 240x240 
The code used to control the ST7789 was lifted and slightly modified from here: https://embeddedexpert.io/?p=1215

The firmware will first display a file named "card.bin", and display a brief message.
Then it will cycle through all images in the root directory of the SD Card.

Images on the SD Card should be copied into the root directory.
Images need to be:
 - In binary format (.bin)
 - 270x270x2 format (RGB565)
 
I resized my images using the Windows 11 Power Tools resizing utility (https://learn.microsoft.com/en-us/windows/powertoys/image-resizer).
Use the "Stretch" setting to get the entire image in frame.
After that I converted the JPEG files to PNG using an online drag and drop utility (Google is your friend).
After that I used a Python script to convert the PNG files to RGB565 (https://github.com/jimmywong2003/PNG-to-RGB565).

I would suggest using bi-directional voltage level converters for the LCD Display (( [PSOC5LP]-5V <-> 3.3V-[IPS 240*240] )).
I used Sparkfun BOB-12009 converters (https://www.sparkfun.com/products/12009) which seems to be limited to 10MHz signals.
The IP 240x240 can handle SPI signals up to 25MHz, so you may wish to find more suitable converters.
