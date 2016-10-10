DIR_INC = ./include
DIR_SRC = ./src
DIR_OBJ = ./output
DIR_BIN = ./bin

SRC = $(wildcard $(DIR_SRC)/*.cpp)
NON_DIR = $(notdir $(SRC))
OBJ = $(NON_DIR:%.cpp=$(DIR_OBJ)/%.o)
#OBJ = $(patsubst %.cpp,$(DIR_OBJ)/%.o,$(NON_DIR))

CC = g++
CFLAGS = -g -Wall -I$(DIR_INC)
TARGET = KMonitorClient
BIN_TARGET = $(DIR_BIN)/$(TARGET)

$(BIN_TARGET):$(OBJ)
	$(CC) $(OBJ) -o $@

$(DIR_OBJ)/%.o:$(DIR_SRC)/%.cpp
	$(CC) $(CFLAGS) -c $< -o $@

.PHONY:clean
clean:
	find $(DIR_OBJ) -name *.o | xargs rm -rf {}
