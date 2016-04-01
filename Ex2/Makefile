#VAPTH src include
vpath %.c src
vpath %.h include

PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))
CC := $(PREFIX)/gcc
CFLAGS = -I include

TARGET := main

main: main.o timeutil.o wdshow.o
	$(CC) $^ -o $@ 

main.o: main.c wdshow.h
	$(CC) $(CFLAGS) -c $< 

wdshow.o: wdshow.c wdshow.h timeutil.h
	$(CC) $(CFLAGS) -c $< 

timeutil.o: timeutil.c timeutil.h
	$(CC) $(CFLAGS) -c $< 
	
clean:
	rm *.o $(TARGET)
