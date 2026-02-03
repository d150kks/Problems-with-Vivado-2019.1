# Problems-with-Vivado-2019.1

## Problem with simulator on Ubuntu 20.04

### Problem 1
```bash
ERROR: [XSIM 43-3409] Failed to compile generated C file xsim.dir/testbench_behav/obj/xsim_1.c. 
ERROR: [XSIM 43-3915] Encountered a fatal error. Cannot continue. Exiting...
```

Go to simulator directory in project

*.sim/sim_1/behav/xsim/

Open elaborate.sh and copy the line starting with xvlog, example:

```bash
xvlog --incr --relax -prj testbench_vlog.prj 2>&1 | tee compile.log
```

Open a terminal in this directory, paste the copied line, and add -v 2 at the end. Run it. 
It can be found that real reasons are missing the Libncurses library.
