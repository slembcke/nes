CFLAGS += -Wall -Wextra
CXXFLAGS += -Wall -Wextra
CXXFLAGS += -fno-exceptions -fno-rtti
LDFLAGS += -Wl,-as-needed -Wl,-O1

.phony: all clean
all: png2chr chr2png sametiles tilecoords nes2hex pngreorder png2gba \
	palstat coord2metasprite nesasmc nsf2data text2data \
	coord2lz4

png2chr: png2chr.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

png2gba: png2gba.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

chr2png: chr2png.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

sametiles: sametiles.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

tilecoords: tilecoords.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

nes2hex: nes2hex.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

pngreorder: pngreorder.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

palstat: palstat.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS) -lpng

coord2metasprite: coord2metasprite.o common.o

nesasmc: nesasmc.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

nsf2data: nsf2data.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

text2data: text2data.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

coord2lz4: coord2lz4.o common.o lz4hc.o lz4.o

clean:
	rm -f *.o png2chr chr2png sametiles tilecoords nes2hex pngreorder png2gba palstat \
		coord2metasprite nesasmc nsf2data text2data coord2lz4
