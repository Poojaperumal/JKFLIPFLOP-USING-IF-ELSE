# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
 Developed by: POOJA.P  RegisterNumber: 212224100041

module Ex7(j, k, clk, rst, q, qbar);
    input j;
    input k;
    input clk;
    input rst;
    output q;
    output qbar;
     reg q;
     reg qbar;
     always @ (posedge(clk) or posedge(rst))  begin
     if (rst==1'b1)
     begin
     q=1'b0;
     qbar=1'b1;
     end
     else if (j==1'b0 && k==1'b0)
     begin
     q=q;
     qbar=qbar;
     end
     else if (j==1'b0 && k==1'b1)
     begin
     q=1'b0;
     qbar=1'b1;
     end
     else if (j==1'b1 && k==1'b0)
     begin
     q=1'b1;
     qbar=1'b0;
     end
     else
     begin
     q=~q;
     qbar=~qbar;
     end
     end    
     endmodule

     
**RTL LOGIC FOR FLIPFLOPS**

![Screenshot 2025-05-12 085919](https://github.com/user-attachments/assets/d735ed45-18f3-42a0-9147-d0dbac00091a)


**TIMING DIGRAMS FOR FLIP FLOPS**

![Screenshot 2025-05-12 090153](https://github.com/user-attachments/assets/67986de1-d255-457d-9014-77fa67407661)

**RESULTS**

Thus the JK flipflop is verfied in Quartus Successfully.
