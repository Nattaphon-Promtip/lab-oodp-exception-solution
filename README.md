Lab - Exceptions
==========

Before you start
----------
The purpose of this lab is to practice Java programming and basic object oriented programming. You will also learn how to develop Java source and unit testing it. In this project, it contains two sub-folders. **src/main** contains the source code that you have to complete. **src/test** contains unit testing script that helps to check your exercises.


Exercise One - Try & Catch
-------------
Please read the following code and answer the questions. You do not need Eclipse for this.
1. Rewrite the following code, adding an appropriate try-catch block to it with proper exception class.

```java
private​ ​ void​ tryCatch02() {
	int​ ​ num1​ = 120, ​ num2​ = 120, ​ result​ = 0;
	result​ = ​ num2​ / (​ num1​ - ​ num2​ );
	System.​ out ​ .println(​ "Result: "​ + ​ result​ );
}
```
```java
Your code
private void tryCatch02() {
    int num1 = 120, num2 = 120, result = 0;

    try {
        result = num2 / (num1 - num2);
        System.out.println("Result: " + result);
    } catch (ArithmeticException e) {
        System.out.println("Error: Division by zero is not allowed.");
        System.out.println("Exception message: " + e.getMessage());
    }
}
```

2.What is the output of the following code, when tryCatch06() is called?

```java
private void tryCatch06() {
	try {
		try06(0, "");
		System.out.println("A");
	} catch (ArithmeticException e) {
		System.out.println("B Error");
	}
}

private void try06(int num, String s) {
	System.out.println("C");
	try {
		num = s.length();
		num = 200 / num;
	} catch (NullPointerException e) {
		System.out.println("E Error");
	}
	System.out.println("F");
}
```

```
Your answer
C
B Error
```

3. What is the output of the following code, when ​ tryCatch08()​ is called?

```java
private​ ​ void​ tryCatch08() {
	try​ {
		try08(0, ​ null​ );
		System.​ out ​ .println(​ "A"​ );
	} ​ catch​ (NullPointerException ​ e ​ ) {
		System.​ out ​ .println(​ "B"​ );
	}
}
private​ ​ void​ try08(​ int​ ​ num​ , String ​ s ​ ) {
	System.​ out ​ .println(​ "C"​ );
	try​ {
		num​ = ​ s ​ .length();
		System.​ out ​ .println(​ "D"​ );
	} ​ finally​ {
		System.​ out ​ .println(​ "E"​ );
	}
		System.​ out ​ .println(​ "F"​ );
	}
}
```

```java
Your answer
C
E
B
```

Exercise Two - Arrays and Exception
-------------
In the *lab.oodp.exception package*, ArraysAndExceptions.java contains the beginnings of a program which should generate an array of five random integers. The program should then allow the user to enter an index, and should print out the element in the generated array at the supplied index. Complete the program by following these steps:

1. Complete the generateArray() method, which should generate and return the array of
random numbers.
2. Create three new classes – InvalidIndexException, IndexTooLowException, and
IndexTooHighException. These should all be checked exceptions (i.e. extend the
Exception class).
3. Modify the *getArrayIndex* method. This method convert given String into int (using Integer.parseInt() method) and return it. It throws these three exceptions appropriately:

 * InvalidIndexException should be thrown when the given String is not an integer number.
 * IndexTooLowException should be thrown when the converted integer number is too small to be a valid index.
 * IndexTooHighException should be thrown when the converted integer number is too large to be a valid index.
 
4. Handle these exceptions in the start() method appropriately. If one is caught, the user should be told of their error and be allowed to try again.

Here is the sample of runing ArraysAndExceptions.

```
Enter an index:
>> -5
Error: Index too low!
Enter an index:
>> 10
Error: Index too high!
Enter an index:
>> 3
The element at index 3 is: 736
```

Please test this program with *TestArraysAndExceptions.java*.

Submit this lab
------------------
You can submit this lab by simply pushing the code to the Github. 
