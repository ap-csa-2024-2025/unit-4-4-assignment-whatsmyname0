# unit-4-4-assignment

## Git Config
```
git config user.name "user"
git config user.email "email"
```

## Compiling and Running Java Programs
Note that since the shape classes are separate classes, you will need to compile ALL the files (at least one time).  You can do this by running
```
javac *.java
```
The star means to compile every file that is a Java file type.

Run your code by running
```
java Main.java
```

After you compile the shape classes, you only need to compile and run `Main.java` as usual.

# Instructions  

## Problem 1
Write a program which takes a String input and then prints the number of times the letter p is followed by a vowel (y is not considered a vowel here). Assume that your entire input is entered in lower case.

Sample run
```
Input String:
Peter Piper picked a pack of pickle peppers.
Contains p followed by a vowel 8 times.
```

## Problem 2
The five most common letters in the English alphabet are e, t, a, i, o. Write a program which takes a string input and then prints the same string without the five most common letters in the English alphabet (e, t, a, i o).  Assume your String input is in all lowercase.

Hint: one good way to do this is to make a new String variable and add all the letters you want to print (i.e. everything except the five most common letters) to it.

Sample Run:
```
Enter a string:
Peter Piper picked a pack of pickle peppers.
pr ppr pckd  pck f pckl ppprs.
```

## Problem 3
Take two String inputs of the same length and merge these two strings in reverse order by taking one character from each String (starting with the second string entered) and alternating. If the Strings are not the same length, the program should print "error".

Sample Run 1:
```
Enter two strings:
balloon
atrophy
ynhopoolrltaab
```
Sample Run 2:
```
Enter two strings:
terrible
mistake
error
```

## Sample Solutions
```java
// Problem 1
Scanner sc = new Scanner(System.in);
String input;
int count = 0;

System.out.println("Input String:");
input = sc.nextLine();

for (int i = 0; i < input.length()-1; i++)
{
  String pair = input.substring(i, i+2);
  if (pair.equals("pa") || pair.equals("pe") || pair.equals("pi") || pair.equals("po") || pair.equals("pu"))
  {
    count++;
  }
}

System.out.println("Contains p followed by a vowel " + count + " times.");

// Problem 2
Scanner sc = new Scanner(System.in);
String input;
String other = "";

System.out.println("Input String:");
input = sc.nextLine();

for (int i = 0; i < input.length(); i++)
{
  String ch = input.substring(i, i+1);
  if (! (ch.equals("e") || ch.equals("t") || ch.equals("a") || ch.equals("i") || ch.equals("o")) )
  {
    other += ch;
  }
}
System.out.println(other);

// Problem 3
Scanner sc = new Scanner(System.in);
String str1;
String str2;
String output = "";

System.out.println("Enter two strings:");
str1 = sc.nextLine();
str2 = sc.nextLine();

if (str1.length() == str2.length())
{
  for (int i = str1.length()-1; i >= 0; i--)
  {
    output += str2.substring(i, i+1) + str1.substring(i, i+1);
  }
}
else
{
  System.out.println("error");
}

System.out.println(output);
```
