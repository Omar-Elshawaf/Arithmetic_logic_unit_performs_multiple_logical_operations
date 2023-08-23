# Arithmetic_logic_unit_performs_multiple_logical_operations
CSE111 Logic Design course Major Task Phase 1
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 I am designing and implementing my own ALU that will take 2 numbers (A, B) as inputs (4-bits each) and will
output the result on 7-segment display. The user will be able to select which function to perform. I have
done the following operations:
1- Addition
2- Subtraction
3- Multiplication
4- AND
5- OR
6- Complement A
7- Increment A

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
First to be implemented is
1- Addition
2- Subtraction
which will be one circuit only with a control (M) if user input is zero the addition operation works, if input equal to one,  subtraction operation will work.
* We’re going to implement addition using 4 Dual 4-to-1 Multiplexers (74153)
* According to the truth table of the adder and to implement using multiplexer, we’re going to make 2 bits as selector and one of them as input but will have some logic gates before it enters multiplexer.
* The dual 4-to-1 multiplexer will have 2 outputs, one for the sum (output bit), and one for the carry (which will be carry in in full adder but here will go as selector to 2nd mux).
* Since we have 8 options and want to implement a 4-to-1, we must divide the 8 options into 4 groups and bring an equation of the sum and carry in terms of the input

![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/d38ea972-4721-45e9-a780-2f0128498fb2)


  We will repeat this 4 times for 4 bits 


Simulation implementation 


![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/818b8ede-6a27-4b53-8487-ec1e2458fbb2)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
3- AND Operation:
To bring output, we’re just going to use an AND IC to do an AND operation for each 2 corresponding bits of the inputs
Example : 
(A0 AND B0) , (A1 AND B1), (A2 AND B2), (A3 AND B3)

 The circuit will be : 

![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/b436ca63-a1f7-4eeb-9cd5-a2d1a4ab28b6)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
4- OR Operation:
To bring output, we’re just going to use an OR IC to do an OR operation for each 2 corresponding bits of the inputs
Example : 
(A0 OR B0) , (A1 OR B1), (A2 OR B2), (A3 OR B3)

 The circuit will be : 


![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/ab5edf70-89fd-4ff3-aba6-a2d0ff4697aa)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
5-Multiplication Operation:
* We’re going to implement multiplication using AND ICs and 4-bit full adders (4 AND IC and 3 4-bit full
adders)
* Here’s the circuit we’re talking about:



![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/9b3e01c6-797d-4a96-92f1-68a0c3bd0b00)


Now, the problem is how we’re going to display the output on 7-segment since here we need 3 of them
 After searching, we’ve found a circuit called double dabble circuit, this is a way which can be used to
display a number on 3 7-segments

 This is the double dabble circuit:


![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/bb6af99a-5f90-48a2-90b8-9f5e11f00966)


To present the number on 3 (7-segments), we’ve found out that we need to repeat the circuit above 7
times, but to make it easier, we’ve created a sub-circuit (our own IC) in proteus to ease things up
 Here’s our IC (sub-circuit):


![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/e58a7173-a321-4814-b027-2b14e5ebc198)



 Now, here’s the full circuit to display on 3 7-segments:

In this image our input were A (1111) which means 15 in binary representation multiplied by B (1111) which means 15 in binary representation, which equals 15*15= 225. 






![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/e2f26ca5-9e6e-462f-bbcd-f1253a120bb9)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
6- Increment Operation:
 We’re going to implement increment operation the same way as we did in addition using 4
multiplexers, but the difference is that the 2nd number won’t be input B, it’ll always be 1
 So, here’s the circuit:


![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/34d5270d-93eb-4561-a41e-239c1a01896f)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
7- Complement Operation:
To bring complement, instead of using not, we’re going to use an XOR IC, where each input bit will be XOR with 1 to give the complement.
Here is its sinulation diagram:

![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/d07c9362-ed72-4f40-9116-e3d0f5eb5056)



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
8- Putting the operations together:
 Now, we’ve done every operation by itself, time to put them together
 We’ve decided that instead of controlling or selecting the output using multiplexers, we can do that using switches : Every switch's output is connected to a circuit which determines is the number bigger than 9 or not to exclude a carry over which will be essential for 7SEG display 
Here is Bigger than 9 circuit detector :

![image](https://github.com/Omar-Elshawaf/Arithmetic_logic_unit_performs_multiple_logical_operations/assets/75243392/fe438023-9a98-4169-9224-0edfce263320)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


THIS PROJECT WAS DONE IN ABOUT 52 HOURS OVER A PERIOD OF TIME 10 DAYS 

THIS PROJECT WAS DONE BY 

    Name                         ID
    
1- Omar ElShawaf Abdelmohsen   21P0410


2- Mohamed Mohamed Taha        21P0137



THIS PROJECT WAS DONE UNDERSUPERVISION OF DR. MOHAMED OMAR ELSHALAKANI 



