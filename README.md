# 25961_StevenBadaga_sunday_evening
# Java Exception Handling


**Types of Exceptions**


**Checked Exceptions**

These are checked at compile-time and must be either declared in a method/constructor's throws clause or caught in a try-catch block.

Examples:

1.IOException: Errors during input/output operations.

2.FileNotFoundException: File not found during an operation.

3.EOFException: End of file reached unexpectedly.

4.SQLException: Database access errors.

5.ClassNotFoundException: Missing class in the classpath.




**Unchecked Exceptions**



These occur at runtime and can be anticipated and recovered from in a well-written application.

Examples:

1.ArithmeticException: Errors in arithmetic operations (e.g., division by zero).

2.NullPointerException: Accessing methods or properties on a null object.

3.ArrayIndexOutOfBoundsException: Invalid index in an array.

4.ClassCastException: Invalid typecasting.

5.IllegalArgumentException: Invalid arguments passed to a method.

6.NumberFormatException: Invalid string to number conversion.



**Detailed Explanation of Exception Handling**


Throwing Exceptions: Code is written to intentionally trigger exceptions (e.g., dividing by zero).

Catching Exceptions: Using try-catch blocks to handle exceptions and prevent program crashes.

Log and Recover:

Print error messages to the console.

Implement fallback mechanisms or alternative flows where applicable.

Best Practices
Ensure programs don't crash by handling exceptions.

Log errors for debugging and user feedback.

Avoid catching generic Exception; catch specific ones.

Use finally blocks for cleanup operations (e.g., closing files).

Validate input data to prevent exceptions.
1.IOException

import java.io.*;



public class IOExceptionExample {

    public static void main(String[] args) {

        try {

            BufferedReader reader = new BufferedReader(new FileReader("nonexistentfile.txt"));

            reader.readLine();

        } catch (IOException e) {

            System.out.println("IOException occurred: " + e.getMessage());

        }

    }

}
2. FileNotFoundException

import java.io.*;



public class FileNotFoundExceptionExample {

    public static void main(String[] args) {

        try {

            FileInputStream file = new FileInputStream("nonexistentfile.txt");

        } catch (FileNotFoundException e) {

            System.out.println("FileNotFoundException occurred: " + e.getMessage());

        }

    }

}

3. EOFException

import java.io.*;



public class EOFExceptionExample {

    public static void main(String[] args) {

        try {

            DataInputStream input = new DataInputStream(new FileInputStream("example.txt"));

            while(true) {

                System.out.println(input.readUTF());

            }

        } catch (EOFException e) {

            System.out.println("EOFException occurred: End of file reached.");

        } catch (IOException e) {

            System.out.println("IOException occurred: " + e.getMessage());

        }

    }

}

4. SQLException

import java.sql.*;



public class SQLExceptionExample {

    public static void main(String[] args) {

        try {

            Connection conn = DriverManager.getConnection("jdbc:invalid-url", "user", "password");

        } catch (SQLException e) {

            System.out.println("SQLException occurred: " + e.getMessage());

        }

    }

}

5. ClassNotFoundException

public class ClassNotFoundExceptionExample {

    public static void main(String[] args) {

        try {

            Class.forName("com.nonexistent.Class");

        } catch (ClassNotFoundException e) {

            System.out.println("ClassNotFoundException occurred: " + e.getMessage());

        }

    }

}

6. ArithmeticException

public class ArithmeticExceptionExample {

    public static void main(String[] args) {

        try {

            int result = 10 / 0;

        } catch (ArithmeticException e) {

            System.out.println("ArithmeticException occurred: " + e.getMessage());

        }

    }

}

7. NullPointerException

public class NullPointerExceptionExample {

    public static void main(String[] args) {

        try {

            String str = null;

            str.length();

        } catch (NullPointerException e) {

            System.out.println("NullPointerException occurred: " + e.getMessage());

        }

    }

}

8. ArrayIndexOutOfBoundsException

public class ArrayIndexOutOfBoundsExceptionExample {

    public static void main(String[] args) {

        try {

            int[] array = new int[5];

            int number = array[10];

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("ArrayIndexOutOfBoundsException occurred: " + e.getMessage());

        }

    }

}

9. ClassCastException

public class ClassCastExceptionExample {

    public static void main(String[] args) {

        try {

            Object x = new Integer(0);

            System.out.println((String)x);

        } catch (ClassCastException e) {

            System.out.println("ClassCastException occurred: " + e.getMessage());

        }

    }

}

10. IllegalArgumentException

public class IllegalArgumentExceptionExample {

    public static void main(String[] args) {

        try {

            Thread t = new Thread();

            t.setPriority(100);

        } catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException occurred: " + e.getMessage());

        }

    }

}

11. NumberFormatException

public class NumberFormatExceptionExample {

    public static void main(String[] args) {

        try {

            int num = Integer.parseInt("XYZ");

        } catch (NumberFormatException e) {

            System.out.println("NumberFormatException occurred: " + e.getMessage());

        }

    }

}



