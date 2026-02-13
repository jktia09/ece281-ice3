# ECE 281 ICE 3: Ripple-Carry Adder with Top Level Design

This is a **template** repository.

[ICE 3 instructions](https://usafa-ece.github.io/ece281-book/ICE/ICE3.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Vivado 2024.2

---

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/`.

Then it **elaborates** the entity defined by `$TB_ENTITY`

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.



![this is my digital waveform for a ripple carry adder](waveform.png)
![this is my sketch of the ripple adder with the switches and LEDs](topbasys.png)

## Documentation 
For this assignment, I utilized the lesson/example in class to declare my ripple adder in top_basys3.vhd. Also, I asked C3C Sangalge if declaring the component of the top-level design was the same as declaring it as an entity and she advised that I replace entity with "component." Also, for the port maps, I initially had red squiggles and she recommended that I end the ripple_adder_inst with a ); in line 89. I did not utilize other resources.
