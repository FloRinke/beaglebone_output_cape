## copy/paste
AA 55 33 EE 41 31 4f 75 74 70 75 74 43 61 70 65 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 30 30 31 41 46 6c 6f 72 69 61 
6e 20 52 69 6e 6b 65 00 00 00 4f 75 74 70 75 74 
43 61 70 65 56 31 00 00 00 00 00 1D 32 35 32 31 
4f 43 56 31 30 30 30 30 00 00 00 00 00 00 00 00 
80 67 00 00 00 00 00 00 00 00 80 67 80 67 00 00 
00 00 00 00 00 00 00 00 00 00 80 67 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 80 67 00 00 80 67 00 00 80 67 00 00 00 00 
80 67 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 80 67 00 00 80 67 00 00 80 67 
00 00 00 00 00 00 00 00 00 00 00 00 80 67 00 00 
00 00 00 00 00 00 00 00 80 67 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 00 
00 00 01 F4

## summary
Header								  0 	  4 						AA 55 33 EE
EEPROM Revision						  4 	  2 	"A1"				41 31
Board Name							  6 	 32 	"OutputCape" 		4f 75 74 70 75 74 43 61 70 65 00 00 00 00 00 00
																		00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
Version								 38 	  4 						30 30 31 41
Manufacturer 						 42 	 16     "Florian Rinke"		46 6c 6f 72 69 61 6e 20 52 69 6e 6b 65 00 00 00
Part Number							 58		 16     "OutputCapeV1" 		4f 75 74 70 75 74 43 61 70 65 56 31 00 00 00 00
Number of Pins						 74 	  2 	29					00 1D
Serial Number (WWYY&&&&nnnn)		 76 	 12 	2521OCV10000		32 35 32 31 4f 43 56 31 30 30 30 30
Pin Usage							 88 	148		29					00 00 00 00 00 00 00 00 80 67 00 00 00 00 00 00
																		00 00 80 67 80 67 00 00 00 00 00 00 00 00 00 00
																		00 00 80 67 00 00 00 00 00 00 00 00 00 00 00 00
																		00 00 00 00 00 00 00 00 00 00 80 67 00 00 80 67
																		00 00 80 67 00 00 00 00 80 67 00 00 00 00 00 00
																		00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 67
																		00 00 80 67 00 00 80 67 00 00 00 00 00 00 00 00
																		00 00 00 00 80 67 00 00 00 00 00 00 00 00 00 00
																		80 67 00 00 00 00 00 00 00 00 00 00 00 00 00 00
																		00 00 00 00
VDD_3V3B Current					236 	  2 	3					00 03
VDD_5V Current						238		  2 	0 					00 00
SYS_5V Current						240		  2 	0					00 00
DC Supplied							242		  2 	500					01 F4
Available							244		32543   zeros				zeros

## full description
### EEPROM Data Format

Header								  0 	  4 	0xAA, 0x55, 0x33, 0xEE

EEPROM Revision						  4 	  2
Revision number of the overall
format of this EEPROM in ASCII
=A1

Board Name							  6 	 32
Name of board in ASCII so user can
read it when the EEPROM is
dumped. Up to developer of the
board as to what they call the
board..

Version								 38 	  4
Hardware version code for board
in ASCII. Version format is up to
the developer. i.e. 02.1…00A1…
.10A0

Manufacturer 						 42 	 16
ASCII name of the manufacturer.
Company or individual’s name.

Part Number							 58		 16
ASCII Characters for the part
number. Up to maker of the board.

Number of Pins						 74 	  2
Number of pins used by the
daughter board including the
power pins used. Decimal value of
total pins 92 max, stored in HEX.

Serial Number						 76 	 12
Serial number of the board. This is
a 12 character string which is:
WWYY&&&&nnnn
where: WW = 2 digit week of the
year of production
YY = 2 digit year of production
&&&&=Assembly code to let the
manufacturer document the
assembly number or product. A
way to quickly tell from reading
the serial number what the board
is. Up to the developer to
determine. nnnn = incrementing
board number for that week of
production

Pin Usage							 88 	148
Two bytes for each configurable
pins of the 74 pins on the
expansion
connectors MSB LSB
Bit order: 15..14 ….. 1..0
Bit 15….Pin is used or not…
0=Unused by cape 1=Used by cape
Bit 14-13…Pin Direction…..1
0=Output 01=Input 11=BDIR
Bits 12-7…Reserved……..should be
all zeros
Bit 6….Slew Rate …….0=Fast 1=Slow
Bit 5….Rx Enable…….0=Disabled
1=Enabled
Bit 4….Pull Up/Dn Select…
.0=Pulldown 1=PullUp
Bit 3….Pull Up/DN enabled…
0=Enabled 1=Disabled
Bits 2-0 …Mux Mode Selection…
Mode 0-7

VDD_3V3B Current					236 	  2
Maximum current in milliamps.
This is HEX value of the current in
decimal
1500mA=0x05 0xDC 325mA=0x01 0x45

VDD_5V Current						238		  2
Maximum current in milliamps.
This is HEX value of the current in
decimal
1500mA=0x05 0xDC 325mA=0x01 0x45

SYS_5V Current						240		  2
Maximum current in milliamps.
This is HEX value of the current in
decimal
1500mA=0x05 0xDC 325mA=0x01 0x45

DC Supplied							242		  2
Indicates whether or not the board
is supplying voltage on the VDD_5V
rail and the current rating 000=No
1-0xFFFF is the current supplied
storing the decimal
equivalent in HEX format

Available							244		32543
Available space for other non-
volatile codes/data to be used as
needed by the manufacturer or SW
driver. Could also store presets for
use by SW.

Bit 15 PIN USAGE is an indicator and should be a 1 if the pin is used or 0 if it is unused.
Bits 14-7 RESERVED is not to be used and left as 0.
Bit 6 SLEW CONTROL 0=Fast 1=Slow
Bit 5 RX Enabled 0=Disabled 1=Enabled
Bit 4 PU/PD 0=Pulldown 1=Pullup.
80Bit 3 PULLUP/DN 0=Pullup/pulldown enabled
1= Pullup/pulldown disabled
Bit 2-0 MUX MODE SELECT Mode 0-7. (refer to TRM)
Refer to the TRM for proper settings of the pin MUX mode based on the signal selection to be used.
The AIN0-6 pins do not have a pin mux setting, but they need to be set to indicate if each of the pins
is used on the cape. Only bit 15 is used for the AIN signals.

### EEPROM Pin Usage
Bit 15 		PIN USAGE 		is an indicator and should be a 1 if the pin is used or 0 if it is unused.
Bit	14-7 	RESERVED 		is not to be used and left as 0.
Bit 6 		SLEW CONTROL 	0=Fast 1=Slow
Bit 5 		RX Enabled 		0=Disabled 1=Enabled
Bit 4 		PU/PD 			0=Pulldown 1=Pullup.
Bit 3 		PULLUP/DN 		0=Pullup/pulldown enabled 1= Pullup/pulldown disabled
Bit 2-0 	MUX MODE SELECT Mode 0-7. (refer to TRM)
Refer to the TRM for proper settings of the pin MUX mode based on the signal selection to be used.
The AIN0-6 pins do not have a pin mux setting, but they need to be set to indicate if each of the pins
is used on the cape. Only bit 15 is used for the AIN signals.

+++15141312
Offset	Conn 	Name 		USE 	Pin 	Type +	Reserved +	
 88		P9-22	UART2_RXD	0000
 90		P9-21	UART2_TXD	0000
 92		P9-18	I2C1_SDA	0000
 94		P9-17	I2C1_SCL	0000
 96		P9-42	GPIO0_7		8067
 98		P8-35	UART4_CTSN	0000
100		P8-33	UART4_RTSN	0000
102		P8-31	UART5_CTSN	0000
104		P8-32	UART5_RTSN	0000
106		P9-19	I2C2_SCL	8067
108		P9-20	I2C2_SDA	8067
110		P9-26	UART1_RXD	0000
112		P9-24	UART1_TXD	0000
114		P9-41	CLKOUT2		0000
116		P8-19	EHRPWM2A	0000
118		P8-13	EHRPWM2B	0000
120		P8-14	GPIO0_26	0000
122		P8-17	GPIO0_27	8067
124		P9-11	UART4_RXD	0000
126		P9-13	UART4_TXD	0000
128		P8-25	GPIO1_0		0000
130		P8-24	GPIO1_1		0000
132		P8-5G	PIO1_2		0000
134		P8-6G	PIO1_3		0000
136		P8-23	GPIO1_4		0000
138		P8-22	GPIO1_5		0000
140		P8-03	GPIO1_6		0000
142		P8-04	GPIO1_7		0000
144		P8-12	GPIO1_12	0000
146		P8-11	GPIO1_13	8067
148		P8-16	GPIO1_14	0000
150		P8-15	GPIO1_15	8067
152		P9-15	GPIO1_16	0000
154		P9-23	GPIO1_17	8067
156		P9-14	EHRPWM1A	0000
158		P9-16	EHRPWM1B	0000
160		P9-12	GPIO1_28	8067
162		P8-26	GPIO1_29	0000
164		P8-21	GPIO1_30	0000
166		P8-20	GPIO1_31	0000
168		P8-18	GPIO2_1		0000
170		P8-07	TIMER4		0000
172		P8-09	TIMER5		0000
174		P8-10	TIMER6		0000
176		P8-08	TIMER7		0000
178		P8-45	GPIO2_6		0000
180		P8-46	GPIO2_7		0000
182		P8-43	GPIO2_8		8067
184		P8-44	GPIO2_9		0000
186		P8-41	GPIO2_10	8067
188		P8-42	GPIO2_11	0000
190		P8-39	GPIO2_12	8067
192		P8-40	GPIO2_13	0000
194		P8-37	UART5_TXD	0000
196		P8-38	UART5_RXD	0000
198		P8-36	UART3_CTSN	0000
200		P8-34	UART3_RTSN	0000
202		P8-27	GPIO2_22	0000
204		P8-29	GPIO2_23	8067
206		P8-28	GPIO2_24	0000
208		P8-30	GPIO2_25	0000
210		P9-29	SPI1_D0		0000
212		P9-30	SPI1_D1		0000
214		P9-28	SPI1_CS0	0000
216		P9-27	GPIO3_19	8067
218		P9-31	SPI1_SCLK	0000
220		P9-25	GPIO3_21 	0000
222		P9-39	AIN0		0000
224		P9-40	AIN1		0000
226		P9-37	AIN2		0000
228		P9-38	AIN3		0000
230		P9-33	AIN4		0000
232		P9-36	AIN5		0000
234		P9-35	AIN6		0000
