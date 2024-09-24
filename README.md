# Half Adder Circuit

A half adder is a circuit meant to compute the first place of binary addition.

![Diagram of binary addition compared to a half adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfadderdiagram.png)

In the diagram, the half adder (HA) takes two inputs, A and B, as the two binary numbers to add. The **S**um is outputted through **S**, and **C**<sub>out</sub> is the digit to **C**arry. The half adder itself is made with two logic gates: a XOR and an AND gate. The XOR gate handles the sum, while the AND gate determines the carry value.

![Diagram of a half adder using logic gates](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddergates.png)

Since a half adder is made with logic gates, it can be recreated with integrated circuits. The integrated circuits I'll be using are simply multiple logic gates packed onto one chip. I'll use the circuit diagram below to construct a simple half adder circuit.

![Circuit diagram of a half adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuitdiagram.png)

![Constructed half adder circuit](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit0%2B0.png)

In the above image, the half adder is adding two binary zeros together. This explains why both the S and C<sub>out</sub> LEDs are off; 0 + 0 returns a Sum of 0 and a Carry value of 0. If we wanted to change the bits we're adding together, we just have to flip the first or last switch. Below, I flip switch B on so that I'm adding 0 and 1 together.

![Half adder circuit with switch B on](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit0%2B1.png)

This combination illuminates the S LED because 0 + 1 equals 1. Both of these examples make sense, but something interesting happens when we flip both inputs on.

![Half adder circuit with both switches active](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit1%2B1.png)

Since we can't represent a binary 2 with a single LED, we have to turn the Sum LED back off again and *carry* the extra to the next place of addition. This is similar to how you can't add any integer to 9 without making it at least two digits long (i.e. 9 + 1 = 10, 9 + 6 = 15). The only difference here is that we only have *two* states to count with, hence *binary*; while in normal math we have *ten* states to count with (0 through 9), hence *decimal*.
