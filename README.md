# Focaccia-Board
 A Multipurpose Breakout for the FT232H
 
 P.S. I am going to ask WHID-Injector & WHID-Elite manufacturer if interested to bring it to life at the usual affordable price for the folks out there that have no time or capabilities to print the PCB themselves. #StayTuned & Follow @whid-injector on Twitter!
 
# Bill-of-Materials
Please check the BOM.txt for the components needed. Most likely (except the R470OHM 2010) you may have all you need already.

# Tips:<br>
- This breakout is designed for the FT232H CJMCU board (https://www.aliexpress.com/item/32814913865.html)<br>
- Pull-up Resistors are 470 Ohm.<br>
- Screws to hold the PCB to the 3D-printed case are 2x6mm.<br>
- You can select the working Voltage by moving the Jumper on the PCB (i.e. Voltage Selector)<br>

## UART
Command to run the UART console feature:
Configure minicom/putty/whatever-terminal-you-are-used-to (e.g. ```screen /dev/ttyUSB0 38400```)

## JTAG
Command to run the JTAG debugging feature:

```sudo openocd -f ft232h_jtag-swd.config  -f target_device.cfg```

## SWD
Command to run the SWD debugging feature (remember to uncomment last line in ft232h_jtag-swd.config):

```sudo openocd -f ft232h_jtag-swd.config  -f target_device.cfg``` 

## SPI Dumping
Command to run the SPI dumping feature:

```flashrom -p ft2232_spi:type=232H -r spi_dump.bin```

In case you need also to write a SPI flash... please do enable the WRITE PROTECT (WP) Jumper on the PCB (i.e. SPI WP Enable).

## I2C Dumping

## Multipurpose Pin Headers/Sockets
On the lower part of Focaccia-Board's PCB there are some pin headers/sockets that are not connected with the FT232H. They are there just in case you need to mess-up with many flying-wires and you want to keep all connections clean and in order like with an usual breadboard, but with screwdown terminal blocks & co. 
