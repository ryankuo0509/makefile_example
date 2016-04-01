#---------------------------------------------------------------------
# settings
#---------------------------------------------------------------------
PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))

#vpath %.c libs
#vpath %.h include

# binaries
SRCS = $(wildcard *.c) $(wildcard libs/*.c)
OBJS = $(patsubst %.c, %.o, $(SRCS))

# Output
DEPS = $(patsubst %.o, %.d, $(OBJS))

#---------------------------------------------------------------------
# executables
#---------------------------------------------------------------------
CC := $(PREFIX)/gcc
MKDIR := /bin/mkdir -p
CAT := /bin/cat

CFLAGS = -g -MMD -I ./include 

-include $(DEPS)
#---------------------------------------------------------------------
# Build Rules
#---------------------------------------------------------------------
TARGET = test

$(TARGET): $(OBJS)
	$(CC) -o $@ $^

clean:
	rm -rf *.o *.a *~ $(TARGET) $(OBJS) $(DEPS)
