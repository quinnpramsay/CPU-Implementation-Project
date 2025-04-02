# CPU-Implementation-Project

For our Computer Systems course, we were assigned a CPU implementation project focused on designing and building key processor components. Our goal was to develop a fully functional Arithmetic Logic Unit (ALU) and Register File capable of handling 32-bit operations. These components needed to efficiently communicate and process data throughout the system, ensuring accurate computation and seamless interaction within the CPU architecture.

# ALU Design

When designing the ALU, we started by creating two 32-bit input pins to help visualize its effectiveness and ensure the outputs were correct. For the adder, we connected these input pins to an arithmetic adder, then linked the adder’s output to the first input of a multiplexer. The multiplexer was then connected to a 32-bit output pin. To control which arithmetic operation was selected, we also connected a 3-bit selector pin to the multiplexer.
We followed a similar process for the OR and AND gates. For the equality operation, we first used an XNOR gate to send an output to the multiplexer, ensuring the arithmetic operation was processed correctly. Once we confirmed this, we connected the original inputs to a comparator, which then linked to an LED output that indicated whether the two input values were equal.
The most challenging part was designing the equality operation. There was a lot of trial and error since we weren’t sure which arithmetic function or logic gate to use to get the correct output. Ultimately, we found that using both an XNOR gate and a comparator produced the desired result.

# Challenges with the Register File 

Challenges we faced while working on this register file were with the registers. Specifically, addressing the correct register for read and write. We had to make a 3 to 8 decoder to make sure that only one register was selected for writing. Another problem we encountered was making sure that writing only happens at the right time. To do this, the registers have an individual write enable input. And the decoder activates only one register at a time based on the writing address. 

# Testing the Circuit 

For testing the register file and ALU, we assigned each their own 32-bit input and output pins to help visualize any issues. To ensure both components functioned correctly, we first built and tested them separately before combining them. Once integrated, we conducted a testing process to verify that the outputs remained accurate. We input various random binary numbers and experimented with different values to ensure the outputs were consistent across all cases.


# Optimization 

If we had more time and resources, we likely would have focused on optimizing the register file, ensuring that all seven registers were necessary, and verifying the consistency of the multiplexer’s output. For the ALU, we would have spent more time refining the equality operator. Currently, the output is just an LED light, but we could have made it more sophisticated by implementing a clearer binary output, such as explicitly displaying a one or zero.

# Real World Applications

The ALU and Register File are key parts of modern CPUs, helping them process data quickly and efficiently. In real-world computers, CPUs have multiple ALUs running in parallel to handle more complex tasks like graphics processing and floating-point math. The Register File stores data for fast access, so the CPU doesn’t have to keep grabbing it from slower memory. With optimizations like pipelining and out-of-order execution, these components make computers faster and more efficient, which is important for everything from gaming PCs to smartphones and embedded systems.
