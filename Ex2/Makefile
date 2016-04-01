PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))
CC := $(PREFIX)/gcc

TARGET := main

CFLAGS = -I include

main: main.o timeutil.o wdshow.o
	gcc $^ -o $@ 

main.o: main.c wdshow.h
	gcc $(CFLAGS) -c $< -o $@

wdshow.o: wdshow.c wdshow.h timeutil.h
	gcc $(CFLAGS) -c $< -o $@

timeutil.o: timeutil.c timeutil.h
	gcc $(CFLAGS) -c $< -o $@
	
clean:
	rm *.o $(TARGET)
