# Modify the following two entries accordingly!
TARGET = fig1.3
GLIBCPATH = /home/clay/Share/unix_coding/glibc/install/glibc-2.39/lib

OBJ = $(TARGET).o
SRC = $(TARGET).c
CC = gcc
CFLAGS = -g
LDFLAGS = -nostdlib -nostartfiles -static
GLIBCDIR = $(GLIBCPATH)
STARTFILES = $(GLIBCDIR)/crt1.o $(GLIBCDIR)/crti.o `gcc --print-file-name=crtbegin.o`
ENDFILES = `gcc --print-file-name=crtend.o` $(GLIBCDIR)/crtn.o
LIBGROUP = -Wl,--start-group $(GLIBCDIR)/libc.a -lgcc -lgcc_eh -Wl,--end-group

$(TARGET): $(OBJ)
	$(CC) $(LDFLAGS) -o $@ $(STARTFILES) $^ $(LIBGROUP) $(ENDFILES)

$(OBJ): $(SRC)
	$(CC) $(CFLAGS) -c $^

clean:
	rm -f *.o *.~ $(TARGET)
