# NAME OF EXECUTABLE
NAME = code

# COMPILER
CC = g++
CFLAGS = -Wall -Wextra -Werror -g -std=c++17 -fsanitize=address -g

# DIRECTORIES
SRC_DIR = ./srcs/
OBJ_DIR = ./objs/
OBJ_DIR_CLASS = ./objs/classes
INC_DIR = ./includes/

# HEADERS
HEADERS = -I $(INC_DIR)

# SRCS & OBJS
SRCS = main.cpp \
		classes/class.cpp
OBJS = $(addprefix $(OBJ_DIR),$(SRCS:.cpp=.o))

all: objs $(NAME)

objs:
	mkdir -p $(OBJ_DIR)
	mkdir -p $(OBJ_DIR_CLASS)

$(OBJ_DIR)%.o:$(SRC_DIR)%.cpp
	$(CC) $(CFLAGS) $(HEADERS) -o $@ -c $<

$(NAME):$(OBJS)
	$(CC) $(CFLAGS) -o $(NAME) $(OBJS)

clean:
	rm -rf $(OBJ_DIR)

fclean: clean
	rm -f $(NAME)

re:
	@$(MAKE) fclean
	@$(MAKE) all

.PHONY: all clean fclean re
