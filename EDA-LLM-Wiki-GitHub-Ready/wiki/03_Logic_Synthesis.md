# Logic Synthesis

來源：https://yosyshq.readthedocs.io/projects/yosys/en/stable/using_yosys/synthesis/index.html

Synthesis in detail
¶
Synthesis can generally be broken down into coarse-grain synthesis, and
fine-grain synthesis.  We saw this in
Synthesis starter
where a design was loaded and elaborated and then went through a series of
coarse-grain optimizations before being mapped to hard blocks and fine-grain
cells.  Most commands in Yosys will target either coarse-grain representation or
fine-grain representation, with only a select few compatible with both states.
Commands such as
proc
,
fsm
, and
memory
rely on the additional information
in the coarse-grain representation, along with a number of optimizations such as
wreduce
,
share
, and
alumacc
.
opt
provides optimizations which are
useful in both states, while
techmap
is used to convert coarse-grain cells to
the corresponding fine-grain representation.
Single-bit cells (logic gates, FFs) as well as LUTs, half-adders, and
full-adders make up the bulk of the fine-grain representation and are necessary
for commands such as
abc
/
abc9
,
simplemap
,
dfflegalize
, and
memory_map
.
Synth commands
Packaged
synth_*
commands
General synthesis
Converting process blocks
Example
FSM handling
FSM detection
FSM extraction
FSM optimization
FSM recoding
Memory handling
The
memory
command
Example
Memory mapping
Supported memory patterns
Notes
Simple dual port (SDP) memory patterns
Single-port RAM memory patterns
Read register reset patterns
Asymmetric memory patterns
True dual port (TDP) patterns
Patterns only supported with Verific
Undesired patterns
Optimization passes
The
opt
macro command
Constant folding and simple expression rewriting -
opt_expr
Merging identical cells -
opt_merge
Removing never-active branches from multiplexer tree -
opt_muxtree
Simplifying large MUXes and AND/OR gates -
opt_reduce
Merging mutually exclusive cells with shared inputs -
opt_share
Performing DFF optimizations -
opt_dff
Hierarchical optimization -
opt_hier
pass
Removing unused cells and wires -
opt_clean
pass
When to use
opt
or
clean
Other optimizations
Technology mapping
Cell substitution
Subcircuit substitution
Gate-level technology mapping
The extract pass
The wrap-extract-unwrap method
Example: DSP48_MACC
The ABC toolbox
ABC: the unit delay model, simple and efficient
ABC9: the generalised delay model, realistic and flexible
Setting up a flow for ABC9
specify
syntax
Mapping to cell libraries
A simple counter
Loading the design
Coarse-grain representation
Logic gate mapping
Mapping to hardware
