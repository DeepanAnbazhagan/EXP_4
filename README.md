# EXP_4
# ALU
# Aim:
To stimulate and synthesis 16bit ALU using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
# Block Diagram:

![image](https://github.com/RESMIRNAIR/ALU/assets/154305926/33dff162-59b3-44e2-886a-1ddd6e60979f)

# ALU Arithmetic and Logic Operations
----------------------------------------------------------------------
|ALU_Sel|   ALU Operation
----------------------------------------------------------------------
| 0000  |   ALU_Out = A + B;
----------------------------------------------------------------------
| 0001  |   ALU_Out = A - B;
----------------------------------------------------------------------
| 0010  |   ALU_Out = A * B;
----------------------------------------------------------------------
| 0011  |   ALU_Out = A / B;
----------------------------------------------------------------------
| 0100  |   ALU_Out = A << 1;
----------------------------------------------------------------------
| 0101  |   ALU_Out = A >> 1;
----------------------------------------------------------------------
| 0110  |   ALU_Out = A rotated left by 1;
----------------------------------------------------------------------
| 0111  |   ALU_Out = A rotated right by 1;
----------------------------------------------------------------------
| 1000  |   ALU_Out = A and B;
----------------------------------------------------------------------
| 1001  |   ALU_Out = A or B;
----------------------------------------------------------------------
| 1010  |   ALU_Out = A xor B;
----------------------------------------------------------------------
| 1011  |   ALU_Out = A nor B;
----------------------------------------------------------------------
| 1100  |   ALU_Out = A nand B;
----------------------------------------------------------------------
| 1101  |   ALU_Out = A xnor B;
----------------------------------------------------------------------
| 1110  |   ALU_Out = 1 if A>B else 0;
----------------------------------------------------------------------
| 1111  |   ALU_Out = 1 if A=B else 0;
----------------------------------------------------------------------
# Program:
```
module alu (

input[7:0]A,B,

input[3:0]ALU_SEL,

output reg[7:0]Result

);

always @ (*)

begin  

case(ALU_SEL)

4'b0000:

Result=A+B;

4'b0001:

Result=A-B;

4'b0010:

Result=A*B;

4'b0011:

Result=A/B;

4'b0100:

Result=A>>1;

4'b0101:

Result=A<<1;

4'b0110:

Result={A[6:0],A[7]};

4'b0111:

Result={A[0],A[7:1]};

4'b1000:

Result=A&B;

4'b1001:

Result=A|B;

4'b1010:

Result=A^B;

4'b1011:

Result=~(A|B);

4'b1100:

Result=~(A&B);

4'b1101:

Result=~(A^B);

4'b1110:

Result=(A>B)?8'd1:8'd0;

4'b1111:

Result=(A==B)?8'd1:8'd0;

default: Result=A+B;

endcase

end

endmodule
```
# Output:

![ALU](https://github.com/Douglas0207/ALU/assets/166375742/e34787a5-6d8a-4bed-81fc-cb5a11ad2ee1)

# Result:
Thus the verilog program for 16bit ALU has been simulated and verified successfully.



#  BCD_7SEGMENT
# AIM
To design and simulate BCD 7 Segment using vivado.
# Software Required:
vivado 2023.2 software.
# PROCEDURE
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# BCD_7SEGMENT

![image](https://github.com/RESMIRNAIR/BCD_7SEGMENT/assets/154305926/804ab8db-8637-45ac-b10f-80e77d818d61)

# VERILOG CODE
```
module segment7(
     bcd,
     seg
    );
     
     
     input [3:0] bcd;
     output [6:0] seg;
     reg [6:0] seg;

//always block for converting bcd digit into 7 segment format
    always @(bcd)
    begin
        case (bcd) //case statement
            0 : seg = 7'b0000001;
            1 : seg = 7'b1001111;
            2 : seg = 7'b0010010;
            3 : seg = 7'b0000110;
            4 : seg = 7'b1001100;
            5 : seg = 7'b0100100;
            6 : seg = 7'b0100000;
            7 : seg = 7'b0001111;
            8 : seg = 7'b0000000;
            9 : seg = 7'b0000100;
            //switch off 7 segment character when the bcd digit is not a decimal number.
            default : seg = 7'b1111111; 
        endcase
    end
    
endmodule
```
# OUTPUT

![326367924-68222d42-c4b3-48fa-a8ac-3d43947148aa](https://github.com/Douglas0207/BCD_7SEGMENT/assets/166375742/0caeba77-e567-4402-bfa4-43b338489cd5)

# RESULT
Thus the BCD 7 Segment is verified succcessfully.


