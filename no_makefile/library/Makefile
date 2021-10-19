#This is a Makefile

CC:=gcc
BIN_SRC:=main.c
BIN_OBJ:=$(BIN_SRC:.c=.o)
LIB_SRC:=file_reader.c
LIB_OBJ:=$(LIB_SRC:.c=.o)
LIB:=libfile_reader.so
BIN:=reader

CFLAGS:=-Wall
LIBFLAGS:= -fpic -shared

LDFLAGS:= -lfile_reader

PREFIX?=/usr

.PHONY: all clean install uninstall 

all: $(LIB) $(BIN)

$(LIB): $(LIB_OBJ)
	$(CC) $(CFLAGS) $(LIBFLAGS) -o $@ $^

$(BIN): $(BIN_OBJ)
	$(CC) $(CFLAGS) -o $@ $^ $(LDFLAGS)
 
install:$(LIB)
	install -d $(PREFIX)/include $(PREFIX)/lib 
	install -m 644 $(LIB_OBJ) $(PREFIX)/include
	install -m 644 $(LIB) $(PREFIX)/lib
uninstall:
	$(RM) $(PREFIX)/include/$(LIB_OBJ)
	$(RM) $(PREFIX)/lib/$(LIB)
clean:
	$(RM) $(LIB)
	$(RM) *o
	$(RM) $(BIN)



