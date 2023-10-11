CC = gcc
CFLAGS = -g -Wall -O3
#CFLAGS = -g3 -Wall -O0
INCLUDES = -I../linux/usr/include
LIBS = -lm -lpthread

default: gups-pebs gups-random gups-hotset-move

all: gups-pebs gups-random gups-simple gups-lru gups-lru-swap gups-hotset-move #gups

gups-random: gups-random.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-random gups-random.o zipf.o $(LIBS) -L../src/ -lhemem

gups-small: gups-small.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-small gups-small.o ../timer.o $(LIBS)

gups: gups.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups gups.o zipf.o ../timer.o $(LIBS)

gups-pebs: gups.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-pebs gups.o zipf.o $(LIBS) -L../src/ -lhemem

gups-hotset-move: gups-hotset-move.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-move gups-hotset-move.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-changed: gups-hotset-changed.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-changed gups-hotset-changed.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-changed-90: gups-hotset-changed-90.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-changed-90 gups-hotset-changed-90.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-changed-test: gups-hotset-changed-test.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-changed-test gups-hotset-changed-test.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-move-private: gups-hotset-move-private.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-move-private gups-hotset-move-private.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-move-malloc: gups-hotset-move-malloc.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-move-malloc gups-hotset-move-malloc.o zipf.o $(LIBS) -L../src/ -lnuma

gups-hotset-move-malloc-populate: gups-hotset-move-malloc-populate.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-hotset-move-malloc-populate gups-hotset-move-malloc-populate.o zipf.o $(LIBS) -L../src/ -lnuma

gups-simple: gups.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-simple gups.o zipf.o $(LIBS) -L../src/ -lhemem-simple

gups-lru: gups.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-lru gups.o zipf.o $(LIBS) -L../src/ -lhemem-lru

gups-lru-swap: gups.o
	$(CC) $(CFLAGS) $(INCLUDES) -o gups-lru-swap gups.o zipf.o $(LIBS) -L../src/ -lhemem-lru-swap

gups-random.o: gups-random.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-random.c zipf.c

gups.o: gups.c zipf.c  gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups.c zipf.c

gups-hotset-move.o: gups-hotset-move.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-move.c zipf.c

gups-hotset-changed.o: gups-hotset-changed.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-changed.c zipf.c

gups-hotset-changed-90.o: gups-hotset-changed-90.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-changed-90.c zipf.c

gups-hotset-changed-test.o: gups-hotset-changed-test.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-changed-test.c zipf.c

gups-hotset-move-private.o: gups-hotset-move-private.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-move-private.c zipf.c

gups-hotset-move-malloc.o: gups-hotset-move-malloc.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-move-malloc.c zipf.c

gups-hotset-move-malloc-populate.o: gups-hotset-move-malloc-populate.c zipf.c gups.h
	$(CC) $(CFLAGS) $(INCLUDES) -c gups-hotset-move-malloc-populate.c zipf.c

clean:
	$(RM) *.o gups gups-hotset-move gups-hotset-single-thread gups-lru-swap gups-lru gups-simple gups-random gups-pebs gups-hotset-move-private gups-hotset-move-malloc gups-hotset-move-malloc-populate gups-hotset-changed gups-hotset-changed-90 gups-hotset-changed-test
