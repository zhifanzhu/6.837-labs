INCFLAGS  = -I /usr/include/GL
INCFLAGS += -I ../vecmath/include

LINKFLAGS  = -lglut -lGL -lGLU
LINKFLAGS += -L ../vecmath/lib -lvecmath

CFLAGS    = -O2 -std=c++11
DEBUG 	 ?= 0
ifeq ($(DEBUG), 1)
	CFLAGS += -O0 -g -DDEBUG
else
	CFLAGS += -O2
endif
CC        = g++
SRCS      = main.cpp
OBJS      = $(SRCS:.cpp=.o)
PROG      = a0

all: $(SRCS) $(PROG)

$(PROG): $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) -o $@ $(INCFLAGS) $(LINKFLAGS)

.cpp.o:
	$(CC) $(CFLAGS) $< -c -o $@ $(INCFLAGS)

depend:
	makedepend $(INCFLAGS) -Y $(SRCS)

clean:
	rm $(OBJS) $(PROG)

