# 32Bit-ALU_Synthesis

## Aim:

Synthesize 32 Bit ALU design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

### Step 2 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

module alu_32bit_tb_case;
reg [31:0]a;

reg [31:0]b;

reg [2:0]f;

wire [31:0]y;

alu_32bit_case test2(.y(y),.a(a),.b(b),.f(f));

initial

begin

a=32'h00000000;

b=32'hFFFFFFFF;

#10 f=3'b000;

#10 f=3'b001;

#10 f=3'b010;

#10 f=3'b100;

end

initial

#50 $finish;

endmodule

#### Synthesis RTL Schematic :
![Screenshot 2024-11-16 112556](https://github.com/user-attachments/assets/f628fcf7-377c-4e9f-a774-fdbe3eb0da1c)
#### Area report:
![Screenshot 2024-11-16 112714](https://github.com/user-attachments/assets/d31764bb-f1f4-4fd4-91ab-ca27bb6b22a6)
#### Power Report:
![Screenshot 2024-11-16 112650](https://github.com/user-attachments/assets/255428a0-5b92-491b-9d11-306cd84d895d)
#### Result: 

The generic netlist of 32 bit ALU  has been created, and area, power reports have been tabulated and generated using Genus.
