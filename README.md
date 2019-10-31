# ps3
CS 22 Data Structures

## Part 2
http://sites.harvard.edu/~cscie22/problem_sets/ps3.shtml


### Problem 5: Rewriting linked-list methods
30 points

If you haven’t already done so, complete the steps above to prepare for this and the remaining problems in Part II.

In lecture, we’ve been looking at linked lists of characters that are composed of objects from the StringNode class. The class includes a variety of methods for manipulating these linked lists, and many of these methods provide functionality that is comparable to the methods found in Java String objects.

Some of the existing StringNode methods use recursion, while others use iteration (i.e., a loop!). In this problem, you will rewrite several of the methods so that they use the alternative approach.

Guidelines

The revised methods should have the same method headers as the original ones. Do not rename them or change their headers in any other way.

Global variables (variables declared outside of the method) are not allowed.

Make sure to read the comments accompanying the methods to see how they should behave.

Because our StringNode class includes a toString() method, you can print a StringNode s in order to see the portion of the linked-list string that begins with s. You may find this helpful for testing and debugging. However, you may not use the toString() method as part of any of your solutions.

More generally, you must not use any of the other StringNode methods in your solutions. Rather, your methods should do all of the work on their own.

Make your methods as efficient as possible. For example, you should avoid performing multiple traversals of the linked list if your task could be performed using a single traversal.

Another useful method for testing is the convert() method, which converts a Java String object into the corresponding linked-list string.

There is existing test code in the main() method. Leave that code intact, and use it to test your new versions of the methods. You are welcome to add extra test code to this method, although doing so is not required.

You can also test your revised methods from the Interactions Pane in DrJava. For example:

> StringNode s1 = StringNode.convert("hello");
> StringNode.indexOf(s1, 'l')
2
A general hint: Drawing diagrams will be a great help as you design your revised methods.

Before you get started, we recommend that you put a copy of the original StringNode class in a different folder, so that you can compare the behavior of the original methods to the behavior of your revised methods.

Rewrite the indexOf() method. Remove the existing recursive implementation of the method, and replace it with one that uses iteration instead.

Rewrite the toUpperCase() method. Remove the existing iterative implementation of the method, and replace it with one that uses recursion instead. No loops are allowed.

Rewrite the isPrefix() method so that it uses iteration. Remove the existing recursive implementation of the method, and replace it with one that uses iteration instead.

Rewrite the insertAfter() method. Remove the existing iterative implementation of the method, and replace it with one that uses recursion instead. No loops are allowed.

Rewrite the copy() method. Remove the existing recursive implementation of the method, and replace it with one that uses iteration instead.

Remember: Draw diagrams to help you in your work!


### Problem 6: More fun with StringNodes
10 points; required of grad-credit students; “partial” extra credit for others

The guidelines for Problem 5 also apply here.

Rewrite the removeAllSpaces() method so that it uses iteration. Remove the existing recursive implementation of the method, and replace it with one that uses iteration instead.

Add a new method with the following header:

public static StringNode replace(StringNode str, char oldChar, char newChar)

It must use recursion to create and return a new linked-list string in which all occurrences of the character oldChar in the string represented by str are replaced by the character newChar.

The method must be fully recursive, and it must not change the original linked list. For example:

> StringNode s1 = StringNode.convert("banana");
> StringNode s2 = StringNode.replace(s1, 'a', 'o');
> System.out.println(s2);
bonono
> System.out.println(s1);   // original should be unchanged
banana



### Problem 7: Implementing the Bag ADT using a linked list
18 points

Earlier in the course, we worked with the ArrayBag class, which implements the Bag interface using an array.

In a file named LLBag.java, write a class called LLBag that implements the Bag interface using a linked list instead of an array. You may use a linked list with or without a dummy head node.

In designing your implementation, you may find it helpful to compare the LLList class, our linked-list implementation of the List ADT, to the ArrayList class, our array-based implementation of that same ADT. In the same way that LLList uses a linked list instead of an array to implement a list, your LLBag class should use a linked list instead of an array to implement a bag.

Notes:

Make sure that your class explicitly indicates that it implements the Bag interface, which we have included in the ps3 folder. To allow your new class to compile, you will need to put your LLBag.java file in the ps3 folder as well.

Like the LLList class, your LLBag class should use a private inner class called Node for the nodes in the linked list.

In addition to the methods in the Bag interface, your LLBag class should also have a toString() method that overrides the default toString() method inherited from the Object class. Consult the ArrayBag toString() method to see what the string returned by this method should look like.

One of the benefits of using a linked list is that there is no need to specify a maximum size—the bag can effectively grow without limit. Therefore, you will not need to provide a constructor that specifies a maximum size, and your add() method can always return true.

Because the order of the items in a bag doesn’t matter, you can add items to either end of the linked list; however, make sure that your method adds items in O(1) time.

In general, you should make your methods as efficient as possible. For example, when implementing the remove() method, you should make sure that you don’t traverse the list more than once.

Copy over the main() method from the ArrayBag class, and make whatever modifications are necessary to allow it to test your LLBag class.

Important: If you compare the results that you obtain from testing the two classes, you may see that the items are not in the same order in both sets of tests. That is to be expected, and it’s not a problem because items in a bag do not have a position!


### Problem 8: Palindrome tester
12 points

We will cover the material needed for this problem on October 16.

A palindrome is a string like "radar", "racecar", and "abba" that reads the same in either direction. To enable longer palindromes, we can ignore spaces, punctuation, and the cases of the letters. For example:

"A man, a plan, a canal, Panama!"
is a palindrome, because if we ignore spaces and punctuation and convert everything to lowercase we get

"amanaplanacanalpanama"
which is a palindrome.

In the file Problem8.java that we’ve included in the ps3 folder, add a static method called isPal() that takes a String object as a parameter and determines if it is a palindrome, returning true if it is and false if it is not.

A string of length 1 and an empty string should both be considered palindromes. Throw an exception for null values.

Although this problem could be solved using recursion or an appropriately constructed loop that manipulates the String object directly, your method must use an instance of one or more of the following collection classes from the ps3 folder:

ArrayStack
LLStack
ArrayQueue
LLQueue
You must not use any other data structure, including arrays or linked lists other than the ones that are “inside” instances of the above collections. Rather, you should put individual characters from the original string into an instance of one or more of the above collections, and use those collection object(s) to determine if the string is a palindrome.

For full credit, you should:

Write your method so that spaces, punctuation, and the cases of the letters don’t prevent a string from being a palindrome. To put it another way, make sure that your method only considers characters in the string that are letters of the alphabet and that it ignores the cases of the letters. See our example above.

Make your method as efficient as possible. In particular:

You should perform only one iteration over the original String object. After that one iteration, any additional manipulations of the characters should be done using the collection object(s) that you have chosen to use.

Because we want to avoid unnecessary scanning, you may not use any of the built-in String methods except charAt() and length().

Hints:

When constructing the collection object(s) that you decide to use, you will need to specify the appropriate data type for the items in the collection. Because char values are primitives, you should use the corresponding “wrapper” class, which is called Character.

You may also find it helpful to use the Character.toLowerCase() or Character.toUpperCase() method.

Remember that char values are essentially integers, so you can compare them just as you would compare integers.
