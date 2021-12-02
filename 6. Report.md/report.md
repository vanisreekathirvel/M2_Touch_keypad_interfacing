## RESEAECH 

we are going to interface a 4x2 (8 key) touch keypad with ATMEGA328 microcontroller. We all know keypad is one of the most important input devices used in electronics engineering. This module does not have actual keys, but have specially designed capacitive metal pads, and these pads are very sensitive by this method, this will provide easy solution.

## DEFINING SYSTEM

when a person gets in contact with one of the pads, there will a capacitive change in the corresponding loop, and this change will be sensed by the control electronic in the module. As a response to the touch the corresponding pad output pin goes high.  

## 4W'S and 1H

WHO

This application is used by all the persons who are all used mobile phones,calculator like electronic cadgets.

WHAT

This helps to maintain the database, send characters and data accordingly.

WHEN  

This is very useful and also it is very tedious to enter the records so here this come to handy.

WHERE 

This is very useful for all over the place especially used in all embedded electronic cadgets.

HOW

This project is implemented to who are all used touch keypad interfacing.

## SWOT Analysis

 *'s' - will opearate the cadgets very easilly
 
 *'w' - initially we are in trouble
 
 *'o' - will easily uses the cadgets by touching
 
 *'T' - a lot more pins and more inputs 
 
## REQUIREMENTS

high level requirements

numbers

character
 
string
 
low level requirements

input supply

delay

## IMPLMENTATION

#include <avr/io.h>

//header to enable data flow control over pins

#define F_CPU 1000000      

//telling controller crystal frequency attached

#include <util/delay.h>

//header to enable delay function in program

#define    E   5

//giving name “enable”  to 5th pin of PORTD, since it Is connected to LCD enable pin

#define RS  6

//giving name “registerselection” to 6th pin of PORTD, since is connected to LCD RS pin

void send_a_command(unsigned char command);

void send_a_character(unsigned char character);

void send_a_string(char *string_of_characters);    

int main(void)

{

DDRB = 0xFF;

// putting portB and portD as output pins

DDRD = 0xFF;

DDRA = 0;//porta as input

_delay_ms(50);//giving delay of 50ms

int key=0;//allocating integer to reset the LCD once it reaches its display limit

int keypressed=0;//integer for storing matrix value

send_a_command(0x01); //Clear Screen 0x01 = 00000001

_delay_ms(50);

send_a_command(0x38);//telling lcd we are using 8bit command /data mode

_delay_ms(50);

send_a_command(0b00001111);//LCD SCREEN ON and courser blinking

send_a_string("PRESS A KEY");//displaying a string

send_a_command(0x80 + 0x40 +0);// moving courser to second line of LCD

while(1)

{

if (bit_is_set(PINA,0))

{

send_a_string("1");//if pin0 goes high show” 1”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,1))

{

send_a_string("2");// if pin1 goes high show” 2”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,2))

{

send_a_string("3");// if pin2 goes high show” 3”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,3))

{

send_a_string("4");// if pin3 goes high show” 4”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,4))

{

send_a_string("5");// if pin4 goes high show” 5”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,5))

{

send_a_string("6");// if pin5 goes high show” 6”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,6))

{

send_a_string("7");// if pin6 goes high show” 7”

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,7))

{

send_a_string("8");// if pin7 goes high show” 8”

_delay_ms(220);

key++;

}

if (key==16)//if 16 characters are shown on LCD

{

send_a_command(0x01); //clear lcd

send_a_string("PRESS A KEY");//display string

send_a_command(0x80 + 0x40 +0);//move courser to second line.

key=0;

}

}

}

void send_a_command(unsigned char command)

{

PORTA = command;

PORTD &= ~ (1<<RS); //putting 0 in RS to tell lcd we are sending command

PORTD |= 1<<E; //telling lcd to receive command /data at the port

_delay_ms(50);

PORTD &= ~1<<E;//telling lcd we completed sending data

PORTA= 0;

}

void send_a_character(unsigned char character)

{

PORTA= character;

PORTD |= 1<<RS;//telling LCD we are sending data not commands

PORTD |= 1<<E;//telling LCD to start receiving command/data

_delay_ms(50);

PORTD &= ~1<<E;//telling lcd we completed sending data/command

PORTA = 0;

}

void send_a_string(char *string_of_characters)

{

while(*string_of_characters > 0)

{

send_a_character(*string_of_characters++);

}

}
