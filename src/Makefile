HEX2BIN = ../utils/Hex2bin-1.0.12/hex2bin
.PHONY: clean libs libsclean
C_FILES := $(wildcard *.c)
IHX_FILES := $(subst .c,.ihx,$(C_FILES))
COM_FILES := $(subst .ihx,.com,$(IHX_FILES))
AS = sdasz80
CC = sdcc
CCFLAGS = --code-loc 0x0178 --data-loc 0 --disable-warning 196 -mz80 --no-std-crt0 -Iinclude include/crt0msx_msxdos_advanced.rel include/putchar.rel include/getchar.rel

all: libs $(COM_FILES)

libs:
	$(MAKE) -C include

libsclean:
	$(MAKE) -C include clean

%.ihx: %.c
	echo $@ $^
	$(CC) $(CCFLAGS) $^

%.com: %.ihx
	mkdir -p bin
	$(HEX2BIN) -e com $^
	mv $@ bin/

clean: libsclean
	rm -f *.com *.rel *.asm *.lst *.sym *.bin *.ihx *.lk *.map *.noi

test:
	openmsx -machine Boosted_MSXturboR_with_IDE -ext msxdos2 -diska ../emulation/msx-dos/ -script ../emulation/boot.tcl -diskb bin/

# vim:ft=make
#
