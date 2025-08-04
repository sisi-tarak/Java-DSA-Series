# Mastering Decision and Selection Control in Java

### Problem-Solving Without Loops: Complete Strategies, Logic \& Code

## **Introduction**

Decision and Selection Control (DSC) is the backbone of basic programming, based primarily on _if-else_ conditions. In this guide, you'll learn how to tackle four classic programming problems **using only conditions (i.e., without any loops)**. We'll explain the logic, discuss why each technique works, and provide clean, well-commented Java code for each case.

These strategies are not just about coding, but also about thinking logically, analyzing constraints, and understanding the power and limitations of conditionals.

## **Problem 1: Check if a Number is Prime (Using Only Conditions)**

### **Objective**

Determine whether a given number $n$ is a prime, using **no loops**—only decision statements.

### **Strategy \& Logic**

- A prime number has only two divisors: 1 and itself.
- Normally, we'd check divisibility from 2 to $\sqrt{n}$, but without loops, we must limit our checks.
- For **small numbers**, we can:
  - Immediately recognize small primes (2, 3, 5, 7, 11).
  - Test divisibility by those small primes for other numbers.
- This method is **not fully accurate for all numbers**, but is a practical exercise in using just if-else statements.

### **Java Code**

```java
import java.util.Scanner;
// Prime check using only conditions, no loops

public class PrimeCheckNoLoops {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int ip = sc.nextInt();

        // Explicit exceptions for 2, 3, 5, 7, 11
        if(ip == 2 || ip == 3 || ip == 5 || ip == 7 || ip == 11) {
            System.out.println(ip + " is a prime number.");
        } else if(ip < 2) {
            // Numbers less than 2 are not prime by definition
            System.out.println(ip + " is not a prime number.");
        } else if(ip % 2 == 0 || ip % 3 == 0 || ip % 5 == 0 || ip % 7 == 0 || ip % 11 == 0) {
            // Divisible by a small prime, hence not a prime
            System.out.println(ip + " is not a prime number.");
        } else {
            // For all other cases, say it's prime (valid only for small numbers)
            System.out.println(ip + " is a prime number.");
        }
    }
}
```

**Key Takeaways**

- This approach is for learning only—**it won't work for larger numbers**.
- The logic demonstrates the use of **decision control** for simple cases.

## **Problem 2: Check Whether a Character is a Vowel or a Consonant**

### **Objective**

Given a single character, determine if it's a vowel or consonant, considering both lowercase and uppercase.

### **Strategy \& Logic**

- English alphabet has vowels: _a, e, i, o, u_.
- Check for both lowercase and uppercase vowels using multiple OR (`||`) conditions.
- Any alphabetic character **not** a vowel is a consonant (for this context, we’ll assume input is an English letter).

### **Java Code**

```java
import java.util.Scanner;
// Vowel or consonant check with only if-else

public class VowelConsonantCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        char ch = sc.next().charAt(0);

        if(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
           ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') {
            System.out.println(ch + " is a vowel.");
        } else {
            System.out.println(ch + " is a consonant.");
        }
    }
}
```

**Key Takeaways**

- Technique relies on **explicit character comparison**.
- For alphabets only; does **not classify symbols or numbers**.

## **Problem 3: Classify a Character as Vowel / Consonant / Number / Symbol**

### **Objective**

Receive a single character as input, and classify it as:

- Vowel
- Consonant (any English alphabet that is not a vowel)
- Number (digit)
- Symbol (any other character)

### **Strategy \& Logic**

1. **Check for vowels** - same as previous logic.
2. **Check for numbers** - character between '0' and '9'.
3. **Check for letters** - character between 'a' and 'z' or 'A' and 'Z', excluding vowels.
4. **Else**, it's a symbol.

### **Java Code**

```java
import java.util.Scanner;
// Vowel / consonant / number / symbol classifier

public class CharClassifier {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        char ch = sc.next().charAt(0);

        // Check vowels first
        if(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
           ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') {
            System.out.println(ch + " is a vowel.");
        }
        // Check numbers
        else if(ch >= '0' && ch <= '9') {
            System.out.println(ch + " is a number.");
        }
        // Check alphabet range, consonant if not vowel
        else if((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z')) {
            System.out.println(ch + " is a consonant.");
        }
        // Otherwise, symbol
        else {
            System.out.println(ch + " is a symbol.");
        }
    }
}
```

**Key Takeaways**

- The order of checks is important: vowels first, then numbers, then other letters.
- Everything else is correctly labeled as a symbol using the final else.

## **Problem 4: Display Series up to N Divisible by 2, 3, or 5 (Without Loops)**

### **Objective**

Print all numbers up to a user-input limit $N$, **only those** divisible by 2, 3, or 5, **but without using loops**.

### **Strategy \& Logic**

- Normally, a loop would be ideal.
- **Without loops**, can only hardcode conditions for each value up to a practical limit (like 10 or 15).
- For real interviews, be explicit this method is limited and mostly for _learning purpose_.

### **Java Code**

_(Example for N from 0 to 10 only; extend as needed.)_

```java
import java.util.Scanner;
// Display numbers up to N divisible by 2, 3, or 5, no loops

public class DivisibleBy235NoLoops {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();

        // For N up to 10, check and print explicitly
        if(N >= 0 && 0 % 2 == 0) System.out.print("0 ");
        if(N >= 1 && (1 % 2 == 0 || 1 % 3 == 0 || 1 % 5 == 0)) System.out.print("1 ");
        if(N >= 2 && (2 % 2 == 0 || 2 % 3 == 0 || 2 % 5 == 0)) System.out.print("2 ");
        if(N >= 3 && (3 % 2 == 0 || 3 % 3 == 0 || 3 % 5 == 0)) System.out.print("3 ");
        if(N >= 4 && (4 % 2 == 0 || 4 % 3 == 0 || 4 % 5 == 0)) System.out.print("4 ");
        if(N >= 5 && (5 % 2 == 0 || 5 % 3 == 0 || 5 % 5 == 0)) System.out.print("5 ");
        if(N >= 6 && (6 % 2 == 0 || 6 % 3 == 0 || 6 % 5 == 0)) System.out.print("6 ");
        if(N >= 7 && (7 % 2 == 0 || 7 % 3 == 0 || 7 % 5 == 0)) System.out.print("7 ");
        if(N >= 8 && (8 % 2 == 0 || 8 % 3 == 0 || 8 % 5 == 0)) System.out.print("8 ");
        if(N >= 9 && (9 % 2 == 0 || 9 % 3 == 0 || 9 % 5 == 0)) System.out.print("9 ");
        if(N >= 10 && (10 % 2 == 0 || 10 % 3 == 0 || 10 % 5 == 0)) System.out.print("10 ");
        System.out.println();
    }
}
```

**Key Takeaways**

- Suitable for _tiny_ values of N only.
- Perfectly highlights the **limitations of if-else-only logic** for iterative problems.

## **Summary of Techniques \& Strategies**

- **Direct Decisions:** Use of if-else (or switch) for explicit decision-making.
- **Brute Listing:** For limited data or small inputs, conditions can replace loops, but become unwieldy very quickly.
- **Edge Handling:** Always define base cases and exceptions (like primes less than 2, or input outside expected ranges).
- **Order of Conditions:**
  - More specific checks (like vowels) should come before general checks (like letters).
  - Always use `else` for the most “miscellaneous” case (like symbols).

## **Why Learn These Strategies?**

- **Strengthens logical thinking:** When loops aren’t allowed, it forces you to break problems into conditional actions.
- **Interview preparation:** Many quick MCQ or viva questions ask to convert small loops to decisions.
- **Foundation for advanced logic:** These concepts ground your understanding for when you upgrade to loops and functions.

## **How to Use This Guide**

- Use the code blocks as templates in your own Java IDE.
- Practice reading logic out loud—explain each condition as if teaching someone else.
- Extend or modify each program (e.g., support more letters, increase N, handle bad inputs) to deepen your understanding.

## **Closing**

**Decision and selection control is all about analyzing situations and making the right choice in code.**
Mastering these “no loop” challenges will make you sharper not just for interviews, but for all your programming problem-solving!

Feel free to share, practice, and leave your own creative extensions.
Happy coding!

**Prepared for the [Your Channel Name] Community**
_If you enjoyed this material, subscribe and never miss a new episode on the basics and beyond!_

**End of Document**
