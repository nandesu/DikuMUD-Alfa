CFLAGS=-O1 -g -Wall -Werror -Wno-error=deprecated-declarations -Wno-error=implicit-function-declaration -Wno-error=char-subscripts -Wno-unused-but-set-variable -Wno-unused-value -Wno-unused-variable
# bad ideas
CFLAGS+=-Wno-error=parentheses -Wno-error=return-type -Wno-error=pointer-sign -Wno-error=dangling-else -Wno-error=missing-braces -Wno-error=unused-result -Wno-implicit-function-declaration
# good, optional ideas!
CFLAG+=-fsanitize=address -fno-omit-frame-pointer

LDLIBS=-lcrypt

h_files = include/structs.h include/utils.h include/comm.h include/interpreter.h include/db.h include/handler.h include/spells.h include/limits.h

o_files = comm.o act.comm.o act.informative.o act.movement.o act.obj1.o act.obj2.o act.offensive.o act.other.o act.social.o act.wizard.o handler.o db.o interpreter.o utility.o spec_assign.o shop.o limits.o mobact.o fight.o modify.o weather.o spell_parser.o spells1.o spells2.o reception.o constants.o spec_procs.o signals.o board.o mar_fiz_maz.o magic.o changes.o

all: delplay dmserver

dmserver: $(o_files)
	$(CC) $(LDFLAGS) $^ $(LOADLIBES) $(LDLIBS) -o $@

delplay: delplay.o

comm.o: comm.c $(h_files)
act.comm.o: act.comm.c $(h_files)
act.informative.o: act.informative.c $(h_files)
act.movement.o: act.movement.c $(h_files)
act.obj1.o: act.obj1.c $(h_files)
act.obj2.o: act.obj2.c $(h_files)
act.offensive.o: act.offensive.c $(h_files)
act.other.o: act.other.c $(h_files)
act.social.o: act.social.c $(h_files)
act.wizard.o: act.wizard.c $(h_files)
handler.o: handler.c $(h_files)
db.o: db.c $(h_files)
interpreter.o: interpreter.c $(h_files)
utility.o: utility.c $(h_files)
spec_assign.o: spec_assign.c $(h_files)
spec_procs.o: spec_procs.c $(h_files)
limits.o: limits.c $(h_files)
fight.o: fight.c $(h_files)
weather.o: weather.c $(h_files)
shop.o: shop.c $(h_files)
spells1.o: spells1.c $(h_files)
spells2.o: spells2.c $(h_files)
magic.o: spells2.c $(h_files)
spell_parser.o: spell_parser.c $(h_files)
mobact.o: mobact.c $(h_files)
modify.o: modify.c $(h_files)
reception.o: reception.c $(h_files)
constants.o: constants.c $(h_files)
board.o: board.c $(h_files)
list.o: list.c $(h_files)
signals.o: signals.c $(h_files)
mar_fiz_maz.o: mar_fiz_maz.c $(h_files)
changes.o: changes.c $(h_files)

delplay.o: delplay.c include/structs.h

clean:
	rm -f *.o dmserver delplay

