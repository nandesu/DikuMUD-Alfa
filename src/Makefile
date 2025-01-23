CFLAGS=-O1 -g -Wall -Werror -Wno-error=deprecated-declarations -Wno-error=implicit-function-declaration -Wno-error=char-subscripts -Wno-unused-but-set-variable -Wno-unused-value -Wno-unused-variable
# bad ideas
CFLAGS+=-Wno-error=parentheses -Wno-error=return-type -Wno-error=pointer-sign -Wno-error=dangling-else -Wno-error=missing-braces -Wno-error=unused-result -Wno-implicit-function-declaration
# good, optional ideas!
CFLAG+=-fsanitize=address -fno-omit-frame-pointer

LDLIBS=-lcrypt

h_files = include/structs.h include/utils.h include/comm.h include/interpreter.h include/db.h include/handler.h include/spells.h include/limits.h

o_files = comm.o act.comm.o act.informative.o act.movement.o act.obj1.o act.obj2.o act.offensive.o act.other.o act.social.o act.wizard.o handler.o db.o interpreter.o utility.o spec_assign.o shop.o limits.o mobact.o fight.o modify.o weather.o spell_parser.o spells1.o spells2.o reception.o constants.o spec_procs.o signals.o board.o mar_fiz_maz.o magic.o changes.o

libgame.a: $(o_files)
	ar rcs libgame.a $(o_files)
	ranlib libgame.a
	rm -f $(o_files)  # Delete the .o files after adding to the archive

all: delplay dmserver

dmserver: delplay.o libgame.a
	$(CC) $(LDFLAGS) -o $@ $^ $(LOADLIBES) $(LDLIBS)

delplay: delplay.o libgame.a
	$(CC) $(LDFLAGS) -o $@ $^ $(LOADLIBES) $(LDLIBS)

%.o: %.c $(h_files)
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f *.o dmserver delplay libgame.a
