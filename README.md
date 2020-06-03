
# Focaccia-Board
 A Multipurpose Breakout for the FT232H to easily clean and hack (I)IoT devices!
 Read more about it here: https://medium.com/@LucaBongiorni/hacking-iot-devices-with-focaccia-board-8c4e009ed488
 <img src="https://miro.medium.com/max/622/1*vHCtNQX8rzAZNiSN__ZFtQ.jpeg" width=300 align=right>
  
# For Sale on Tindie & Aliexpress
https://www.aliexpress.com/item/4001080780756.html

https://www.tindie.com/products/aprbrother/focaccia-board/

** The Author has no profit out of FocacciaBoard sales. But you can always buy him an Italian Coffee :) 

<a href='https://ko-fi.com/X7X6L82L' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi4.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>
 
# Bill-of-Materials
Please check the BOM.txt for the components needed. Most likely (except the R470OHM 2010) you may have all you need already.<br>
Of course, you still need to purchase a part the FT232H CJMCU (e.g. https://aliexpress.com/item/33052982174.html)

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
