# Exe files
BIN := bin/
# .hpp files
#INC := include/
# .cpp files
SRC := src/
# .o files
OBJ := obj/

COMPILER := g++

FLAGS := -std=c++11

# Source files.
# Add all files to be used in onde project here. 

# Concatenates all files to the project.
CHESS := $(wildcard src/*.cpp)

# Compile project. 
all: create_folders $(CHESS:src/%.c=obj/%.o)
	$(COMPILER) -o bin/chess $(CHESS) $(FLAGS)

create_folders:
	@mkdir -p $(OBJ) $(BIN)

# Generate .o files.
obj/%.o: src/%.cpp
	$(COMPILER) $(FLAGS) -c $< -o $@ -I./include
	$(COMPILER) $(FLAGS) -c ../utils/utils.c -o obj/utils.o -I../utils

# Run the executable files.
run: bin/chess
	bin/chess

.PHONY: clean
clean:
	rm -rf bin/*
	rm -rf obj/*