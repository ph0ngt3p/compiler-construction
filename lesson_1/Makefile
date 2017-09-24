BINARY   = scanner

CC       = gcc
CFLAGS   = -Wall

SRCDIR   = src
OBJDIR   = obj
BINDIR   = bin
TESTDIR  = tests

SOURCES  := $(wildcard $(SRCDIR)/*.c)
INCLUDES := $(wildcard $(SRCDIR)/*.h)
OBJECTS  := $(SOURCES:$(SRCDIR)/%.c=$(OBJDIR)/%.o)

$(BINDIR)/$(BINARY): $(OBJECTS)
	@mkdir -p $(BINDIR)
	${CC} $(OBJECTS) -o $@
	@echo "Executable generated as bin/scanner!"

$(OBJECTS): $(OBJDIR)/%.o : $(SRCDIR)/%.c
	@mkdir -p $(OBJDIR)
	${CC} $(CFLAGS) -c $< -o $@
	@echo "Succesfully compiled $<!"

.PHONY: clean
clean:
	@rm -f $(OBJECTS)
	@echo "Cleanup complete!"

.PHONY: remove
remove:
	@rm -Rf $(BINDIR)
	@rm -Rf $(OBJDIR)
	@echo "All build files removed!"

test: 
	@bin/scanner tests/example${ex}.kpl