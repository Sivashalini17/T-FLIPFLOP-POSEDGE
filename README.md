# EXPERIMENT 9 : T-FLIPFLOP-POSEDGE
DATE :06/12/24
**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/458a68fe-2d08-4a9d-ac4f-7ae0480ce0bd)

 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/cdd7fb32-539f-4b66-bb8d-f305a153c886)

 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**

**PROGRAM**
```
class TFlipFlop:
    def __init__(self):
        self.q = 0  # Initial state of the flip-flop (Q = 0)

    def clock_pulse(self, t):
        """
        Simulates a clock pulse for the T flip-flop.
        If T = 1, it toggles the output (Q).
        If T = 0, the output remains the same.
        """
        if t == 1:  # Toggle the output when T = 1
            self.q = 1 - self.q  # Toggle the state (Q = Q')
        # If T = 0, the state remains unchanged

    def get_state(self):
        """Returns the current state (Q) of the flip-flop."""
        return self.q

def main():
    t_flip_flop = TFlipFlop()
   
    clock_cycles = 5  # Number of clock cycles to simulate
    inputs = [(1,), (0,), (1,), (1,), (0,)]  # T inputs for each clock cycle
    
    for cycle in range(clock_cycles):
        t_input = inputs[cycle][0]  # Get the T input for the current cycle
        print(f"Cycle {cycle + 1}: T input = {t_input}")
        t_flip_flop.clock_pulse(t_input)  # Apply the clock pulse and T input
        print(f"State of Q after cycle {cycle + 1}: {t_flip_flop.get_state()}")
        print("-" * 30)

if __name__ == "__main__":
    main()
```

**RTL LOGIC FOR FLIPFLOPS**
**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/user-attachments/assets/5a4e3c61-3a68-40f7-8261-36aeca78b5d1)

**RESULTS**
therefore the code has been successdully completed
