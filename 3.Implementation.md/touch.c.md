# MAKE FILE

## touch.c

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
