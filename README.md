# Half Adder Circuit

The purpose of this repository is to show my understanding of binary addition and how it applies in theory and in practice. To do this I will explain one of the simplest ways to add two binary numbers together: the half adder. A half adder is a circuit meant to compute the first digit of binary addition. This circuit forms the foundation of more complicated circuits like the full and 4-bit adder.

As a short recap: binary numbers are comprised of only 0's and 1's. This is different than decimal numbers, which are comprised of any digits 0-9. The limited number of digits means that binary numbers grow larger faster than decimal. So 0, 1, 2, 3, 4, 5 in decimal is 0, 1, 10, 11, 100, 101 in binary.

![Diagram of binary addition compared to a half adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfadderdiagram.png)

(Justice, 2020, p. 76)

In the diagram, the half adder (HA) takes two inputs, A and B, as the two binary digits to add. The **S**um is outputted through **S**, and **C**<sub>out</sub> is the digit to **C**arry to the next place value. The half adder itself is made with two logic gates: a XOR and an AND gate. The XOR gate handles the sum, while the AND gate determines the carry value.

![Diagram of a half adder using logic gates](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddergates.png)

(Justice, 2020, p. 77)

Since a half adder is made with logic gates and has a limited number of inputs, we can visualize every possible output it could have with the truth table shown below. With this, we can confirm a number of solutions. For example, 0 + 0 will be equal to 0, and 1 + 1 will return a Sum of 0 with a Carry of 1.

![Truth table for a half adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddertruthtable.png)

(Justice, 2020, p. 77)

With all of this information in mind, we can now recreate a half adder using integrated circuits. The integrated circuits I'll be using are simply multiple logic gates packed onto one chip. I'll use the circuit diagram below to construct a simple half adder circuit.

![Circuit diagram of a half adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuitdiagram.png)

(Justice, 2020, p. 90)

![Constructed half adder circuit](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit0%2B0.png)

In the above image, the half adder is adding two binary zeros together. This explains why both the S and C<sub>out</sub> LEDs are off; 0 + 0 returns a Sum of 0 and a Carry value of 0. If we wanted to change the bits we're adding together, we just have to flip the first or last switch. Below, I flip switch B on so that I'm adding 0 and 1 together.

![Half adder circuit with switch B on](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit0%2B1.png)

This combination illuminates the S LED because 0 + 1 equals 1. Both of these examples make sense, but something interesting happens when we flip both inputs on.

![Half adder circuit with both switches active](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/halfaddercircuit1%2B1.png)

Since we can't represent a binary 2 with a single LED, we have to turn the Sum LED back off again and *carry* the extra to the next place of addition. This is similar to how you can't add any integer to 9 without making it at least two digits long (i.e. 9 + 1 = 10, 9 + 6 = 15). The only difference here is that we only have *two* states to count with, hence *binary*; while in normal math we have *ten* states to count with (0 through 9), hence *decimal*.

A half adder is just one small piece of the puzzle, however. If you want to add more than 1 bit numbers, you'll have to create a full adder, which is used for every binary digit you want to calculate after the first one. A full adder is simply two half adders tied together with an OR gate. This allows the circuit to take three inputs instead of two. The extra input is used for C<sub>in</sub>, aka the carry value from the previous adder.

![Full adder in context](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/fulladderexample.png)
![Diagram of a full adder](https://raw.githubusercontent.com/bedrockskeleton/half-adder/refs/heads/main/images/fulladder.png)
(Justice, 2020, p. 78-79)

Half and full adders chained together allow computers to calculate not only binary numbers, but decimal numbers by extension. A four-bit adder, for example, can handle numbers from 0-15. 0000 in binary represents 0 in decimal, and 1111 in binary represents 15. The cap increases exponentially with every new full adder. This means that an 8-bit adder would be able to handle numbers from 0-255 (0 - 11111111 in binary)! This technology is how the first solid-state transistor calculator, the IBM 608, was created in 1955.

![The IBM 608 calculator](https://www.columbia.edu/cu/computinghistory/608.jpg)

(Cruz, 2001)

While this may look a set of kitchen appliances. This calculator is capable of dealing with up to 18-digit decimal numbers in fractions of a second. All thanks to boards that don't function much differently than the one we created. Of course calculators have become much smaller since then, but early calculators go to show how far we've come in computing power.

![A board from the IBM 608 calculator](https://archive.computerhistory.org/resources/access/physical-object/2012/02/102746916.01.01.lg.JPG)

## References
Cruz, F. (2001, January). The IBM 608 Calculator. Columbia University. Retrieved September 23, 2024, from https://www.columbia.edu/cu/computinghistory/608.html

Justice, M. (2020). How Computers Really Work: A Hands-On Guide to the Inner Workings of the Machine. No Starch Press.
