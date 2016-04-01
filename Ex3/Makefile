#---------------------------------------------------------------------
# settings
#---------------------------------------------------------------------
PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))

#vpath %.c libs
#vpath %.h include
DIR_SRC += ./libs
DIR_INC += ./include

# binaries  
SRCS = $(wildcard *.c) $(wildcard $(DIR_SRC)/*.c)
OBJS = $(patsubst %.c, %.o, $(SRCS))

# Output
DEPS = $(patsubst %.o, %.d, $(OBJS))
#---------------------------------------------------------------------
# executables
#---------------------------------------------------------------------
CC := $(PREFIX)/gcc
MKDIR := /bin/mkdir -p
CFLAGS += -I $(DIR_INC) 
#---------------------------------------------------------------------
# Build Rules
#---------------------------------------------------------------------
TARGET = test

$(TARGET): $(OBJS)
	$(CC) -o $@ $^

clean:
	rm -rf *.o *.a *~ $(TARGET) $(OBJS) $(DEPS)
