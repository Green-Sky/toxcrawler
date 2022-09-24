LIBS = toxcore
CFLAGS = -std=gnu99 -Wall -ggdb -fstack-protector-all -pthread -O2
CFLAGS += -I../../toxcore/
OBJ = main.o util.o
#LDFLAGS = $(shell pkg-config --libs $(LIBS))
LDFLAGS ?= -L../../toxcore/build -ltoxcore
SRC_DIR = ./src

all: $(OBJ)
	@echo "  LD    $@"
	@$(CC) $(CFLAGS) -o crawler $(OBJ) $(LDFLAGS)

%.o: $(SRC_DIR)/%.c
	@echo "  CC    $@"
	@$(CC) $(CFLAGS) -o $*.o -c $(SRC_DIR)/$*.c
	@$(CC) -MM $(CFLAGS) $(SRC_DIR)/$*.c > $*.d

clean:
	rm -f *.d *.o crawler

.PHONY: clean all
