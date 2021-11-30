# HEADER FILE

## touch.h

#ifndef touch.h

#define touch.h

#define F_CPU 1000000      

#define    E   5

#define RS  6

void send_a_command(unsigned char command);

void send_a_character(unsigned char character);

void send_a_string(char *string_of_characters);    

#endif
