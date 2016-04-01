#---------------------------------------------------------------------
# settings
#---------------------------------------------------------------------
vpath %.c src
vpath %.h include
CFLAGS = -I include
PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))

HOST_ROOT    := .
OUTPUT_PATH  := output
#---------------------------------------------------------------------
# executables
#---------------------------------------------------------------------
MKDIR := /bin/mkdir -p
CC := $(PREFIX)/gcc

#---------------------------------------------------------------------
# configs
#---------------------------------------------------------------------

#---------------------------------------------------------------------
# marcro
#---------------------------------------------------------------------
define CREATE_FOLDER
	$(MKDIR) $(OUTPUT_PATH)
endef


#---------------------------------------------------------------------
# Input dirs, names, files
#---------------------------------------------------------------------
TARGET: main.o wdshow.o timeutil.o
	$(call CREATE_FOLDER)
	
main.o: main.c wdshow.h
	$(CC) $(CFLAGS) -c $< 

wdshow.o: wdshow.c wdshow.h timeutil.h
	$(CC) $(CFLAGS) -c $< 

timeutil.o: timeutil.c timeutil.h
	$(CC) $(CFLAGS) -c $< 
	
clean:
	rm -f *.o $(TARGET) 
	rmdir $(OUTPUT_PATH)
