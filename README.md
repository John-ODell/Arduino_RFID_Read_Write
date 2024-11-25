RFID Write and Read by John O'Dell

Items needed
  - Arduino Uno Model (R3, R4 preffered)
  - RFID-RC522 module
  - MIFARE 1k/ 13.56 mhz RFID Cards/FOBS
  - Jumper wire

Download the Arduino IDE at https://www.arduino.cc/en/software
2.x Recommended

If this is your first time using Arduino IDE, take some time to understand the platform.

Libraries Needed:
On the left hand side, click on "Libraries"

  - Search for MFRC522
    - MFRC522 by github community
    - Install all necesscary libraries
  
  - SPI.h should be included
    - search and download if needed

  - If errors pop up of library needed use the search and install in this fasion.

Pin Outs: (Tested on Arduino R4)
  - RST -> 9
  - SDA -> 10
  - MOSI -> 11
  - MISO -> 12
  - SCK -> 13
  - VCC -> 3.3v
  - GND -> GND

"New_Name_RFID.ino"

This file will print te Card/Key ID and the Block 2 (What we are writing). Use this to make sure your cards are blank to prevent writing over.
After writing a new name to a Card/Key use this example again to make sure it wrote correctly

"read_new_name_RFID.ino"

This is the file that will write your Card/Key a new ID in the Block 2 ID.

While the total data we are reading and writing from in Block 2 is 18 the address we are able to write is 15 unique characters with null terminator
We can use number, - and some different special character to point to the addessess in the registry.

It is easiest to keep a 15 character/number name with a null terminator.

After writing the name to the card reload the "read_new_rfid_name.ino", repeating this sketch will continue to rename the card. 

Cards/Keys can be renamed. 

This will not work on Mifare 2 cards. 

Troubleshooting

- After compiling the file onto the arduino, press the reset button to see the print in the serial monitor if does not open automatically
- Check the wiring of the digital in ports
- 3.3v not 5v
- the RFID unit is working correctly, these are best ordered from a good manufacturer
- your Cards/Keys are 13.56 mghz
- the name you have given will work the registry

