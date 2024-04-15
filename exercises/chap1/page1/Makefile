# Makefile for Bluespec compilation and simulation

# Bluespec compiler
BSC = bsc

# Flags for Bluespec compilation
BSC_FLAGS = -verilog

# Simulation executable
SIM_EXE = sim

# Top module name
TOP_MODULE = mkAttempt

# Source file name
BSV_FILE = FirstAttempt.bsv

# Verilog output file name
VERILOG_FILE = mkAttempt.v 

# Main target: simulate the design
simulate: $(SIM_EXE)
	./$(SIM_EXE)

# Rule to compile BSV to Verilog
compile: $(BSV_FILE)
	$(BSC) $(BSC_FLAGS) $(BSV_FILE)

# Rule to link Verilog files and create simulation executable
link: $(VERILOG_FILE)
	$(BSC) -o $(SIM_EXE) -e $(TOP_MODULE) $(VERILOG_FILE)

verify: $(VERILOG_FILE) 
	iverilog $(VERILOG_FILE)

# Clean up generated files
clean:
	rm -f *.v *.bo *.ba *.info *.sched $(SIM_EXE)

# Help message
help:
	@echo "Usage: make [compile|link|simulate|clean|help]"
	@echo "compile    : compile bsv to .v "
	@echo "link       : links .v to sim "
	@echo "simulate   : run simulation"
	@echo "clean      : Remove generated files"
	@echo "help       : Show this help message"

# Phony targets
.PHONY: simulate clean help

