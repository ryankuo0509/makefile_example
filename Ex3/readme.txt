http://wen00072.github.io/blog/2014/03/12/makefile-automatically-assign-a-file-to-a-specific-directory/

$ Original tree
.
├── include
│   ├── liba.h
│   └── libb.h
├── libs
│   ├── liba.c
│   └── libb.c
├── Makefile
└── test.c


[Makefile_1]
	$ After building tree
	.
	├── include
	│   ├── liba.h
	│   └── libb.h
	├── libs
	│   ├── liba.c
	│   └── libb.c
	│   └── liba.o
	│   └── libb.o	
	├── Makefile
	└── test.c
	└── test.o
	└── test	

[Makefile_2]
	$ After building tree
	.
	├── build
	│   ├── libs
	│   │   ├── liba.d
	│   │   ├── liba.o
	│   │   ├── libb.d
	│   │   └── libb.o
	│   ├── test
	│   ├── test.d
	│   └── test.o
	├── include
	│   ├── liba.h
	│   └── libb.h
	├── libs
	│   ├── liba.c
	│   └── libb.c
	├── Makefile
	└── test.c