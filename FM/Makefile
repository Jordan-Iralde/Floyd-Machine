# Compiler and flags
CXX = g++
CXXFLAGS = -Wall -Wextra -std=c++11

# Include and source directories
INCLUDE_DIRS = -I./include
SRC_DIR = ./src
OBJ_DIR = ./build

# Source files
MAIN_SRC = $(SRC_DIR)/main.cpp
GLAD_SRC = ./include/glad/glad.c  # Updated to point to glad.c in the include folder

# Object files
MAIN_OBJ = $(OBJ_DIR)/main.o
GLAD_OBJ = $(OBJ_DIR)/glad.o

# Libraries for GLFW, OpenGL, and dynamic linking
LIBS = -lglfw -ldl -lGL

# Target executable
TARGET = main

# Default target: Compile the project
all: $(TARGET)

# Link the object files and create the executable
$(TARGET): $(MAIN_OBJ) $(GLAD_OBJ)
	$(CXX) $(CXXFLAGS) $(INCLUDE_DIRS) $(MAIN_OBJ) $(GLAD_OBJ) -o $(TARGET) $(LIBS)

# Compile main.cpp into an object file
$(OBJ_DIR)/main.o: $(MAIN_SRC)
	mkdir -p $(OBJ_DIR)
	$(CXX) $(CXXFLAGS) $(INCLUDE_DIRS) -c $(MAIN_SRC) -o $(OBJ_DIR)/main.o

# Compile glad.c into an object file
$(OBJ_DIR)/glad.o: $(GLAD_SRC)
	mkdir -p $(OBJ_DIR)
	$(CXX) $(CXXFLAGS) $(INCLUDE_DIRS) -c $(GLAD_SRC) -o $(OBJ_DIR)/glad.o

# Clean target: Remove the build directory and executable
clean:
	rm -rf $(OBJ_DIR) $(TARGET)
