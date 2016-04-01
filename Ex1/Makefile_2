PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))
  
CC   := $(PREFIX)/gcc


TARGET := main

main: main.o timeutil.o wdshow.o
	$(CC) $^ -o $@
	
main.o: main.c wdshow.h
	$(CC) -c $<

wdshow.o: wdshow.c wdshow.h timeutil.h
	$(CC) -c $<

timeutil.o: timeutil.c timeutil.h
	$(CC) -c $<
	
clean:
	rm *.o $(TARGET)
