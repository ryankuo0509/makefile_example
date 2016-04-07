#---------------------------------------------------------------------
# settings
#---------------------------------------------------------------------
PREFIX := $(firstword $(strip $(foreach e,1 2 3 4 5 6 7 8 9,$(wildcard C:/Progra~$(e)/Sunplus/MIDE-V2.2.0/gnu/bin/))))

# binaries
LIB_SRC=$(shell ls libs/*.c)
SRCS = $(LIB_SRC) $(wildcard *.c)
OBJS = $(patsubst %.c, %.o, $(SRCS))

# Output
OUT_DIR = build
OUT_OBJS = $(addprefix $(OUT_DIR)/, $(OBJS))
DEPS = $(patsubst %.o, %.d, $(OUT_OBJS))

-include $(DEPS)
#---------------------------------------------------------------------
# executables
#---------------------------------------------------------------------
CC := $(PREFIX)/gcc
MKDIR := mkdir -p
CFLAGS += -g -MMD -I ./include 		
       # -MMD:  [.c] -> [.d] for dependency rule
#---------------------------------------------------------------------
# Build Rules
#---------------------------------------------------------------------
TARGET = test

$(OUT_DIR)/$(TARGET): $(OUT_OBJS)
	@echo -Step2
	$(CC) -o $@ $^
	
#---------------------------------------------------------------------------
# Implicit rules
#---------------------------------------------------------------------------
$(OUT_DIR)/%.o:%.c
	@echo -Step1
	$(MKDIR) $(dir $@)
	$(CC) $(CFLAGS) -c $^ -o $@

#---------------------------------------------------------------------------
# dump info
#---------------------------------------------------------------------------	
dump:
	@echo $(SRCS)		 
	@echo $(OBJS)
	@echo $(OUT_OBJS)
	@echo $(DEPS)
    # $(SRCS): 			  libs/liba.c         libs/libb.c   test.c
    # $(OBJS):			  libs/liba.o         libs/libb.o   test.o
    # $(OUT_OBJS): 	build/libs/liba.o   build/libs/libb.o   build/test.o
    # $(DEPS):      build/libs/liba.d   build/libs/libb.d   build/test.d
	
#---------------------------------------------------------------------------
# clean object
#---------------------------------------------------------------------------	
clean:
	rm -rf $(OUT_DIR)


#   #$ Original tree
#   .
#   ¢u¢w¢w include
#   ¢x   ¢u¢w¢w liba.h
#   ¢x   ¢|¢w¢w libb.h
#   ¢u¢w¢w libs
#   ¢x   ¢u¢w¢w liba.c
#   ¢x   ¢|¢w¢w libb.c
#   ¢u¢w¢w Makefile
#   ¢|¢w¢w test.c	
#   	
#   [Makefile_2]
#   $ After building tree
#   .
#   ¢u¢w¢w build
#   ¢x   ¢u¢w¢w libs
#   ¢x   ¢x   ¢u¢w¢w liba.d
#   ¢x   ¢x   ¢u¢w¢w liba.o
#   ¢x   ¢x   ¢u¢w¢w libb.d
#   ¢x   ¢x   ¢|¢w¢w libb.o
#   ¢x   ¢u¢w¢w test
#   ¢x   ¢u¢w¢w test.d
#   ¢x   ¢|¢w¢w test.o
#   ¢u¢w¢w include
#   ¢x   ¢u¢w¢w liba.h
#   ¢x   ¢|¢w¢w libb.h
#   ¢u¢w¢w libs
#   ¢x   ¢u¢w¢w liba.c
#   ¢x   ¢|¢w¢w libb.c
#   ¢u¢w¢w Makefile
#   ¢|¢w¢w test.c	