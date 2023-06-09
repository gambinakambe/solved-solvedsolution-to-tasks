Download Link: https://assignmentchef.com/product/solved-solvedsolution-to-tasks
<br>
###Task 1:

A binary code is a type of code that every entry is either 0 or 1. It is very useful in computer science, cryptography, mathematic and engineering. In the computer system, negative binary code represented by its complement value. For example: *A decimal number (9)10 is (01001)2 of binary number. A decimal number (-9)10 is (-01001)2. In the computer system, the negative value usually represented by its complement value, (10111)2, the most significant (highest) bit is 1, indicates the sign of the value is negative. When the leftmost bit is 0, the sign of the value is positive.* To get the complement value of a negative binary number, we can invert every bit, add 1 on the inverted value of the binary code. For example: *(-9)10 = (-01001)2, to invert binary code, we have (10110)2, to add with 1, we have*“`cpp10110+ 1________10111“`*The complement code of (-01001)2 is (10111)2.*

In this task, you will define a class **BinaryCode** in a file `BinaryCode.h` and implementthe C++ program code in a file `BinaryCode.cpp`.

In the class **BinaryCode**, declare a dynamic array (such as a char pointer or an short integer pointer) to store a binary code, an integer length to store the length of the binary code (includes the sign bit-the most significant bit). Define the following functions in the class BinaryCode.+ In the class BinaryCode, you will define default constructor, copy constructor and other initialization constructors to set initial value for a BinaryCode object;+ In the class BinaryCode, define following overloading operators:– Extraction operator () to get input binary code from keyboard and save it in a BinaryCode object;– Insertion operator (&lt;&lt;) to print out the a BinaryCode stream;– Assignment operator(=) to make a deep copy of BinaryCode object.– Invert operator(!) to invert a BinaryCode object.– Complement operator(~) to make a complement BinaryCode object. A complement of a binary code is its invert plus one.o Addition operator (+) to compute two BinaryCode objects’ addition. You should extend two binary streams to the maximum length of both streams plus one so that the significant bits addition won’t be missed. For example: *Two binary streams (011011)2 + (01111)2 will be extended (0011011)2 + (0001111)2*“`cpp0011011+0001111_________0101010“`– Addition assignment operator (+=) to compute two BinaryCode objects’ addition.– Subtraction operation (-) to compute two BinaryCode objects’ subtraction.The subtraction of two BinaryCode objects is defined as *binaryCode1 – binaryCode2 = binaryCode1 + ~(binaryCode2), where ~ is complement operator.*– Subtraction assignment operator (-=) to compute two BinaryCode objects’ subtraction.– Multiplication operator (*) to compute two BinaryCode objects’ multiplication. To compute the multiplication of two BinaryCode objects, each BinaryCode object should be extended as a signed integer. That is to append number of bits to the left side of a binary stream. Each appended bit’s value should be the value of the most significant bit’s value of the original binary stream. The new length of binary stream is addition of the two binary streams’ length (excludes sign bits). *For example, to compute (01001)2 * (10111)2, we will extend two binary streams to 10 bits (5+5 bits), as (0000001001)2 * (1111110111)2. Then compute*“`cpp1111110111* 0000001001_____________1111110111+1111110111______________10001110101111.“`Keep the last (rightmost) 10 bits as the results, which is (1110101111)2, the complement binary code of (-81)10.– Multiplication assignment operator (*=) to compute two BinaryCodes’ multiplication.– Shift left operator (&lt;&lt;) to shift a BinaryCodes to left a number of bits. For example:

(01011)2 &lt;&lt; 3 will be (01011000)2. It is like (01011)2 * 23.– Shift right operator () to use arithmetic shift method shift a BinaryCode to right a number of bits. For example:

(01011)2 2 will be (010)2. It is like (01011)2 / 2^2.

(1010)2 2 will be (110)2.– Other necessary member functions.

Implement **main()** in a file `task1Main.cpp` to test the functions and operators that defined above (See the Testing examples of the task for more details).

**Testing:**

Use CC to compile the source files on banshee by

$ CC –o task1 task1Main.cpp BinaryCode.cpp

You can test the task by run the program

$ task1

and input data that required. Your program will print out results like following (Data in bold means input from keyboard):Testing example 1:

Input a decimal number for bc1: **1027**

bc1 = 010000000011!bc1 = 101111111100~bc1 = 101111111101bc1 &lt;&lt; 4 = 0100000000110000bc1 2 = 0100000000Input a binary string for bc2: **100110111**

bc2 = 0100110111!bc2 = 1011001000~bc2 = 1011001001bc2 &lt;&lt; 3 = 0100110111000bc2 4 = 010011bc1 + bc2 = 010100111010bc1 – bc2 = 01011001100bc1 * bc2 = 01001101111110100101bc3 = bc1 = 010000000011bc3 += bc2 = 010100111010bc3 = bc1 = 010000000011bc3 -= bc2 = 01011001100bc3 = bc1 = 010000000011bc3 *= bc2 = 01001101111110100101

Testing example 2:

Input a decimal number for bc1: **852**

bc1 = 01101010100!bc1 = 10010101011~bc1 = 10010101100bc1 &lt;&lt; 4 = 011010101000000bc1 2 = 011010101Input a binary string for bc2: **-10100110101001**

bc2 = 101011001010111!bc2 = 010100110101000~bc2 = 010100110101001bc2 &lt;&lt; 3 = 101011001010111000bc2 4 = 10101100101bc1 + bc2 = 101100110101011bc1 – bc2 = 010110011111101bc1 * bc2 = 1011101010101100110001100bc3 = bc1 = 01101010100bc3 += bc2 = 101100110101011bc3 = bc1 = 01101010100bc3 -= bc2 = 010110011111101bc3 = bc1 = 01101010100bc3 *= bc2 = 1011101010101100110001100

Testing example 3:

Input a decimal number for bc1: **-2068**

bc1 = 1011111101100!bc1 = 0100000010011~bc1 = 0100000010100bc1 &lt;&lt; 4 = 10111111011000000bc1 2 = 10111111011Input a binary string for bc2: **-1101110010111001**

bc2 = 10010001101000111!bc2 = 01101110010111000~bc2 = 01101110010111001bc2 &lt;&lt; 3 = 10010001101000111000bc2 4 = 1001000110100bc1 + bc2 = 10001101100110011bc1 – bc2 = 01101010010100101bc1 * bc2 = 0110111101110000011001110100bc3 = bc1 = 1011111101100bc3 += bc2 = 10001101100110011bc3 = bc1 = 1011111101100bc3 -= bc2 = 01101010010100101bc3 = bc1 = 1011111101100bc3 *= bc2 = 0110111101110000011001110100

**Note:** Your program should work on different testing data.

###Task2:

In this task, you will define a class **Date** in a name space **MyLib** in a file `Date.h`. Define data members include day, month and year in the class Date. Define member functions in the class Date. Implement member functions in a file `Date.cpp`. The member functions include+ A function setDate(int, int, int) takes three parameters of day, month and year and set date for the Date object.+ A function setDate(const std::string &amp;) takes a string of date with format “DD/MM/YYYY” and convert the string date to the Date object. “DD/MM/YYYY” represents 2 digits value of day, 2 digits value of month and 4 digits value of year with “/” between them.+ A function validateDate() validates the date of the Date object. If day is invalid, throw an error message “Invalid day. Day should between 1 and **xx**.” (where **xx** is the maximum day for that month). If month is invalid, throw an error message “Invalid month”. If year is invalid, such as less than zero, throw an error message “Invalid year”.+ A function toString() converts day, month and year to a string with format “DD/MM/YYYY”.+ Other necessary function to return date information.

Implement C++ main() function in a file `task2Main.cpp` that test the member functions specified above. It will get date information and set the date to Date objects, validate the date, catch the exception if the date is invalid. See the Testing of this task for details.

**Testing:**

Use CC to compile the source files on banshee by

$ CC –o task2 task2Main.cpp Date.cpp

You can test the task by run the program

$ task2

and input data that required. Your program will print out results like following (Data in bold means input from keyboard):

Input date (DD/MM/YYYY): **29/02/2014**

Invalid day. Day should be between 1 and 28.

Testing example 2:

Input date (DD/MM/YYYY): **30/04/2001**

30/04/2001

Input day: **32**

Input month: **5**

Input year: **2010**

Invalid day. Day should be between 1 and 31.

Testing example 3:

Input date (DD/MM/YYYY): **03/11/2011**

03/11/2011

Input day: **2** **9**

Input month: **2**

Input year: **2000**

29/02/2000

###Task3:

In this task, you will define and implement inheritance classes.

Define the diagrams of the classes below.![fog](https://github.com/GoldOne/See-pei-pei/blob/master/fig_bed/uml%20for%20employee.png)

Define a *base class* **Employee** in a file `Employee.h` that described in the diagrams above. Define an extraction operator () to get input values for an Employee from the keyboard or a file; insertion operator (&lt;&lt;) to print out the Employee information. The data member **DOB is the Date type which has been defined in Task 2**. Define necessary constructor(s) and other member functions for the class. Implement insertion operator, extraction operator, constructor and other member functions in a file `Employee.cpp`.

Define a *derived* class **Administrator** in a file **Administrator.h** that described in the diagrams above. Define an extraction operator () to get input values for an Administrator from the keyboard or a file; insertion operator (&lt;&lt;) to print out the Administrator’s information. ***You should call the extraction operator and insertion operator defined in the base class for those base class’s data members’ input / output***. In the extraction operator, you will catch the exception if the input DOB is invalid. When the exception has been caught, write the administrator information with the error message into a log file `log.txt`.

**Note: Do not terminate the program.**

Define necessary constructor(s) and other member functions for the class. Implement insertion operator, extraction operator, constructor and other member functions in the file **Administrator.cpp**.

Define a *derived class* **Technician** in a file `Technician.h` that described in the diagrams above. Define Extraction operator () to get input values for a Technician from the keyboard or a file; insertion operator (&lt;&lt;) to print out the Technician’s information. ***You should call the extraction operator and insertion operator defined in the base class for those data members’ input / output of the base class***.

In the extraction operator, you will catch the exception if the input DOB is invalid. When the exception has been caught, write the Technician information with the error message into a log file `log.txt`.

**Note: Do not terminate the program.**

Define necessary constructor(s) and other member functions for the class. Implement insertion operator, extraction operator, constructor and other member functions in the file `Technician.cpp`.

Define a *derived class* **Driver** in a file `Driver.h` that described in the diagrams above.Define Extraction operator () to get input values for a Driver from the keyboard or a file; insertion operator (&lt;&lt;) to print out the Driver’s information. ***You should call the extraction operator and insertion operator defined in the base class for those data members’ input / output of the base class***.

In the extraction operator, you will catch the exception if the input DOB is invalid. When the exception has been caught, write the Technician information with the error message into a log file `log.txt`.

**Note: Do not terminate the program.**

Define necessary constructor(s) and other member functions for the class. Implement insertion operator, extraction operator, constructor and other member functions in the file `Technician.cpp`.

Define a class **EmployeeManagemet** in a file `EmployeeManagement.h`. Define two data members: **a dynamic array of Employee pointers**. Each element is a base class Employee pointer that points to a derived class object. Define an integer **length** that stores the total number of Employee objects.

Define constructor(s), destructor and following member functions:+ **loadEmployees(const char *)**: Load all employee records from a given text file and store them in the dynamic array by using extraction operators () for the derived classes Administrator, Technician, Driver and base class Employee.

**Note: The data for employee contain errors, such as wrong date (catch the error) and wrong type of employee. Add the error messages in the file log.txt. Do not stop until the rest of data have been loaded into the dynamic memory.**+ **manageEmployees()**:displays a menu and gets input choices, then call the corresponding member functions to perform the actions.+ **displayEmployees()**: Use insertion operators (defined for the derived classes Administrator, Technician, Driver and base class Employee) to display required Employees’ information that stored in the array.+ **updateEmployee()**: Update an Employee’s information.+ **saveEmployees()**: Save employee data to a given text file.+ Other necessary member functions.

Implement all the member functions defined for the class **EmployeeManagement** in a file `EmployeeManagement.cpp`.

The data format of an employee in a text file are looked like

A,1234567,John Wood,12/02/1965,21 Victoria street Depto NSW 2530,311T,1122334,Taylor Smith,08/04/1978,32 Smith street Wollongong NSW 2500,C++,7D,1234123,Bob Bright,28/09/1983,121 Princess highway Wollongong NSW 2500,1320671

Where ‘A’ represents Administrator type, ‘T’ represents Technician type, and ‘D’ represents Driver type. You can download a text file `employees.txt` for your testing.

Implement C++ main() functions in a file `task3Main.cpp` to get text file name from the command line, declare an instance of EmployeeManagement; then call the instance function **loadEmployees()** to load employee records, call the instance function **manageEmployees()** to perform the activities. Finally save the data to a text file. See the Testing of this task for more details.

**Note: Your program should work on different testing data.**

**Testing:**

Use CC to compile the source files by

$ CC –o task3 task3Main.cpp EmployeeManagement.cpp Employee.cpp Administrator.cpp Technician.cpp Driver.cpp Date.cpp

and run the program by

$ ./task3 employees.txt

When the program starts, it loads data from employees.txt (11 records for this testing file) and displays records (9 correct records) that loaded, then displays menu and get input data (Data in bold denote input data from the keyboard. `&lt;Enter` means the Enter key).

A,1234567,John,12/02/1965,21 Victoria street Depto NSW 2530,311T,1122334,Taylor,08/04/1978,32 Smith street Wollongong NSW 2500,C++,7D,1234123,Bob,28/09/1983,121 Princess highway Wollongong NSW 2500,1320671A,1234568,Marry,20/04/1985,34 Beach Road Fairy Meadow NSW 2500,311D,1122346,Michael,10/10/1970,24 Mall street Wollongong NSW 2500,1230781A,1234590,Rose,20/11/1990,232 Princess highway Unanderra NSW 2526,312D,1234128,Adam,10/12/1987,12 Princess highway Wollongong NSW 2500,1320671T,1122348,Alvin,15/07/1988,48 Spring road Wollongong NSW 2500,Java,8T,1122350,Alice,17/10/1975,33 Autumn street Wollongong NSW 2500,Database,71. Display employees2. Update an employee0. ExitYour choice: **1**

1. Find an employee by a number2. Find all employees by a type0. ExitYour choice: **1**

Input an employee number: **1234567**

A,1234567,John,12/02/1965,21 Victoria street Depto NSW 2530,3111. Find an employee by a number2. Find all employees by a type0. ExitYour choice: **1**

Input an employee number: **1122348**

T,1122348,Alvin,15/07/1988,48 Spring road Wollongong NSW 2500,Java,81. Find an employee by a number2. Find all employees by a type0. ExitYour choice: **1**

Input an employee number: **1122350**

T,1122350,Alice,17/10/1975,33 Autumn street Wollongong NSW 2500,Database,71. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **2**

Input an employee type: **D**

D,1234123,Bob,28/09/1983,121 Princess highway Wollongong NSW 2500,1320671D,1122346,Michael,10/10/1970,24 Mall street Wollongong NSW 2500,1230781D,1234128,Adam,10/12/1987,12 Princess highway Wollongong NSW 2500,13206711. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **2**

Input an employee type: **T**

T,1122334,Taylor,08/04/1978,32 Smith street Wollongong NSW 2500,C++,7T,1122348,Alvin,15/07/1988,48 Spring road Wollongong NSW 2500,Java,8T,1122350,Alice,17/10/1975,33 Autumn street Wollongong NSW 2500,Database,71. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **2**

Input an employee type: **A**

A,1234567,John,12/02/1965,21 Victoria street Depto NSW 2530,311A,1234568,Marry,20/04/1985,34 Beach Road Fairy Meadow NSW 2500,311A,1234590,Rose,20/11/1990,232 Princess highway Unanderra NSW 2526,3121. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **0**

1. Display employees2. Update an employee0. ExitYour choice: **2**

Employee number: **1234567**

A,1234567,John,12/02/1965,21 Victoria street Depto NSW 2530,311

Input new address (Directly Enter for no change): **107 Gipps road Wollongong NSW 2500**

New office (0 for no change): **312**

1. Display employees2. Update an employee0. Exit

Your choice: **1**

1. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **1**

Input an employee number: **1234567**

A,1234567,John,12/02/1965,107 Gipps road Wollongong NSW 2500,3121. Find an employee by a number2. Find all employees by a type0. Exit

Your choice: **0**

1. Display employees2. Update an employee0. Exit

Your choice: **2**

Employee number: **1122350**

T,1122350,Alice,17/10/1975,33 Autumn street Wollongong NSW 2500,Database,7

Input new address (Directly Enter for no change): `&lt;Enter`

New skill level(0 for no change): **9**

1. Display employees2. Update an employee0. Exit

Your choice: **2**

Employee number: **1234128**

D,1234128,Adam,10/12/1987,12 Princess highway Wollongong NSW 2500,1320671

Input new address (Directly Enter for no change): **321 Winter road Sydney NSW 2001**

1. Display employees2. Update an employee0. Exit

Your choice: **0**

Input a file name to save the data: **newemployees.txt**

Bye

The log file `log.txt` contains the following messages:

In the text file line 3 has error: Invalid day. Day should between 1 and 28.In the text file line 9 has an error: ‘S’ is a wrong employee type

The text file `newemployees.txt` contains following data:

A,1234567,John,12/02/1965,107 Gipps road Wollongong NSW 2500,312T,1122334,Taylor,08/04/1978,32 Smith street Wollongong NSW 2500,C++,7D,1234123,Bob,28/09/1983,121 Princess highway Wollongong NSW 2500,1320671A,1234568,Marry,20/04/1985,34 Beach Road Fairy Meadow NSW 2500,311D,1122346,Michael,10/10/1970,24 Mall street Wollongong NSW 2500,1230781A,1234590,Rose,20/11/1990,232 Princess highway Unanderra NSW 2526,312D,1234128,Adam,10/12/1987,321 Winter road Sydney NSW 2001,1320671T,1122348,Alvin,15/07/1988,48 Spring road Wollongong NSW 2500,Java,8T,1122350,Alice,17/10/1975,33 Autumn street Wollongong NSW 2500,Database,9