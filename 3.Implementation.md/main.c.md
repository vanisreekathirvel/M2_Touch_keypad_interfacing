#include <avr/io.h>

#define F_CPU 1000000    

#include <util/delay.h>

#define    E   5

#define RS  6

void send_a_command(unsigned char command);

void send_a_character(unsigned char character);

void send_a_string(char *string_of_characters);    

int main(void)

{

DDRB = 0xFF;

DDRD = 0xFF;

DDRA = 0;

_delay_ms(50);

int key=0;

int keypressed=0;

send_a_command(0x01); 

_delay_ms(50);

send_a_command(0x38);

_delay_ms(50);

send_a_command(0b00001111);

send_a_string("PRESS A KEY");

send_a_command(0x80 + 0x40 +0);

while(1)

{

if (bit_is_set(PINA,0))

{

send_a_string("1");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,1))

{

send_a_string("2");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,2))

{

send_a_string("3");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,3))

{

send_a_string("4");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,4))

{

send_a_string("5");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,5))

{

send_a_string("6");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,6))

{

send_a_string("7");

_delay_ms(220);

key++;

}

if (bit_is_set(PINA,7))

{

send_a_string("8");

_delay_ms(220);

key++;

}

if (key==16)

{

send_a_command(0x01); 

send_a_string("PRESS A KEY");

send_a_command(0x80 + 0x40 +0);

key=0;

}

}

}

void send_a_command(unsigned char command)

{

PORTA = command;

PORTD &= ~ (1<<RS); 

PORTD |= 1<<E; 

_delay_ms(50);

PORTD &= ~1<<E;

PORTA= 0;

}

void send_a_character(unsigned char character)

{

PORTA= character;

PORTD |= 1<<RS;

PORTD |= 1<<E;

_delay_ms(50);

PORTD &= ~1<<E;

PORTA = 0;

}

void send_a_string(char *string_of_characters)

{

while(*string_of_characters > 0)

{

send_a_character(*string_of_characters++);

}

}
