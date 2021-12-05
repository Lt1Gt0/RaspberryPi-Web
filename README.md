# RaspberryPi-Web

Playing around with RFID and database connections

Connected GPIO pins from raspberry pi to RC255
---------------------------------------
System is based off of a Raspberry Pi B3+ with a RC522 RFID module
```
3.3v - 1
RST - 22
GND - 6
IRQ - NONE
MISO - 21 (GPIO 9)
MOSI - 19 (GPIO 10)
SCLK - 23 (GPIO 11)
SDA - 24 (GPIO 8)
```
---------------------------------------
Setting up config.json
---------------------------------------
There is a config.json file that needs to be included with the files that is ignored for saftey reasons
To get around this, create a config.json file with the project
Currently the config.json should contain

`"admin_key": <your_admin_key>`

In terms of the database, right now there is nothing to be added as of this commit
Database might be set up and accessed through python libraries at the moment

Installing the necesarry Packages for python
---------------------------------------
Currently Works only on a raspberry pi B3+ as of now, before running the program open terminal and run

`sudo raspi-config`
activate te SPI interface under "Interfacing Options" the run
`sudo reboot`

after the pi has rebooted, open terminal and run
`lsmod | grep spi`
If `spi_bcm2835` appears everything is set up properly

in terminal to install the necessary python packages run
```
sudo pip3 install spidev
sudo pip3 install mfrc522
```

Now you should be able to run read.py
If everything goes right you should see the id of the card that you put up to the scanner in the termial

---------------------------------------
