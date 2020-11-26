# :1234: Execution Unit

This is a demo of the execution unit built using the simulation program (*Altera Quartus*), the EU unit demo is able to execute the following commands:
* MOVE **Value** to **Register** .
* MOVE **Register** to **Register** (The valuce of the first Reg will be saved in the Second Reg).
* ADD **Value** to **Register** .
* ADD **Register** to **Register** (The Value of the second Reg will be updated with the **Sum** of the Two Registers Values).
* AND **Value** with **Register** .
* AND **Register** with **Register** (The second Register will be updated with the bitwise Anding of the two registers values).

![EU] (EU.JPG)

### Components:
* Three 4-bit Registers **A**, **B**, **C**.
* ALU (Arithmetic Logic Unit).
* Decoding Circuit.

### The Decoded Commands:
The input command to the circuit is 9 bits where:
* First 2 bits are for the operation.
* Third bit is to determine whether the first operand is a register or a value ( *0* for **Register**, *1* for **Value**).
* 4th and 5th bits to determine the second operand Register.
* last 4 bits are for the first operand

| Register | Code| Operation | Code|
| :--------:| :------:|:--------:| :--------:|
| A | 01 | MOVE| 00|
| B| 10| ADD | 10|
| C | 11| AND | 11|

According to that, the final 9-bit input command is decoded as following:
| Command       | Operand 1     | Operand 2     |  Decoded |
| :-----------: | :----------: |:-----------: | :---------:|
| MOV 5, A | 5 | A | 00 1 01 0101|
| ADD A, B | A | B | 10 0 10 0001|
| AND 0, C | 0 | C | 11 1 11 0000|
