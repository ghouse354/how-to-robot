## Varied Variables!

[<< Previous: Say Hello](Hello.md)

------------------------------------------------------------------

**Objectives**: Learn what variables are, and how to write code with them

**Process**:

In the previous lesson, we learned how to output text to the screen using the `System.out.printf()` function. That was fun, but not particularly useful, since everytime you want to changes something, you'll have to rewrite your code. The code we wrote also didn't do very much... So, let's try something a little more exciting and write some code that does some slightly more interesting stuff.

Suppose that your friend has given you a pretty crappy stopwatch that only counts in seconds. Really, it's kinda bad. Can you imagine telling someone else "hey! six hundred and fifty seconds have elapsed"? So, your job is to convert the seconds into hours:minutes:seconds (H:M:S).

Let's try doing this by hand first. Suppose the stopwatch reads 3723. Write out how you would convert this by hand into H:M:S.

.

All good?

.

You should have gotten 1 hour, 2 minutes and 3 seconds. How about the stopwatch instead reads 4123?

Computers are really really good at doing math really really fast, so let's try to write a program that can calculate how many hours, minutes and seconds there are for any given number of seconds.

To start, let's figure out a generic way to solve this problem. There are multiple ways to start (and you may have already used one of these methods when doing it by hand). We could convert the seconds into minutes, and then convert the minutes into hours. Or, we could convert the hours first and figure out how many minutes are left over. There is no right or wrong way to solve this, as long as it works.

For our example, let's use the method that converts from seconds -> minutes -> hours.

First, we'll convert seconds to minutes by dividing by... you guessed it... 60! For 3723, the answer we get is 62 minutes, with 3 seconds left over.

Next, we'll divide the minutes that we calculated previously (in this case, 62) by 60 again, so that we can get the hours. 62 minutes is 1 hour, with 2 minutes left over.

So, we now know that 3723 seconds = 1 hour, 2 minutes, 3 seconds

Cool! What we just worked through is called an *algorithm*, which is a set of steps that a computer (or a human) can take to solve a problem. Now, let's make our *algorithm* a little clearer, and more precise. To do this, we'll write the steps that we took to get our answer in something called *pseudocode*, which kinda looks like English and Math smushed together:

```
Starting Seconds = 3723

Minutes = Starting Seconds / 60 (ignore the remainder)

Seconds = Remainder of (Starting Seconds / 60)

Hours = Minutes / 60 (ignore the remainder)

Minutes = Remainder of (Minutes / 60)

Output Hours, Minutes, Seconds
```

If you're confused, ask for help!

Now that we've broken down how to solve this problem generically, let's try to write some code for it. Here's some [starter code](https://www.ideone.com/f2g1K6).

In the starter code, we see the main function and main body, like in our previous examples. However, we also see something new!

``` java
int seconds;
int hour;
int min;
int sec;

seconds = 3661;
```

What in the world is that? Well, we're declaring **variables**. What are variables you ask? **Variables** are places in your code where you can store *values* (e.g. numbers, text, etc). Different types of variables can store different types of things. For example, if we want to store whole numbers (e.g. -123, 0, 2, 354), we can use an `int` or **Integer**. If we want to hold a number that's NOT a whole number (e.g. 3.14, -0.99, 1.23), we would use a `double`. There are many more *types* than just integers and doubles, but we'll talk about those later.

Now, on the line that says `int seconds;`, we are telling the computer that we would like a place to store a whole number (hence the `int`), and we would like to call it "seconds". The following lines create more *integer* variables with different names.

> In Java, there are basically two parts to a variable. The *type* and the *name*. The *type* tells the computer what kind of values you want to put in the variable, and the *name* tells the computer what you want to refer to the variable as.

OK, cool you say. Now we know how to create variables. But what about this line that says `seconds = 3661;`. What does THAT mean? On that line, we are *assigning* a value to the variable named `seconds` - In this case, we are assigning the value of 3661. Now, `seconds` equals 3661 until we assign it a new value. When we assign values to variables, we ALWAYS put the variables on the left side of the equal sign, and the new value on the right. For example:

```java
int a;
int b;

a = 4;
// Ooh, a is now 4

b = 6;
// Ooh, b is now 6

a = b;
// Uhm what's a now?
```

What do you think the values of `a` and `b` are at the end of this chunk of code? If you guessed that `a` and `b` were both equal to 6, you got it right!

`a` equals 6 because assigning values *always* goes from right to left. The variable on the left side of the equal sign is the variable changing its value. Now, if you try doing this instead `6 = a`, the computer will get incredibly confused, because `6` is not a variable. 6 will always be 6.

Right, now's probably a good time to mess around with some math in code. Open this [math code](https://www.ideone.com/kESOfT) and run it. See what happens! Try changing numbers, can you figure out what is happening?

One thing you may have noticed is that division is a little weird with integers. For example, why does 4 divided by 15 give 0? Why does 15 divided by 4 only give 3? The reason is... we are doing something called *integer math*. This is very much like when you first learned how to do division, where you had things called remainders. (You know, where you divide a number until you're left with something too small to divide by).

With integer division, we don't care about the remainder; We really only care about the main number before the remainder. For example, with 128 / 5, we only care about the 25, and ignore the remainder of 3. By the same logic, 1 / 10 will be 0 with integer division - the answer is 0, remainder 1.

That's great and all, but what if we don't want to be wasteful, and actually *wanted* the remainder? Never fear! there's a special symbol to represent that! In Java, it's the percent sign (%). We call this operation (getting the remainder) *modulus* or *mod*. So, if I wanted the remainder or 10 / 4, and to store that value in the variable `c`, I would write `c = 10 % 4`, or say "c equals 10 mod 4". What could `c` equal to? If you whispered 2, you're right!

Let's make sure that we really understand this. Here are some equations. Write down the answers to each of them, following integer math rules:
- 1 / 10
- 5 % 3
- 2 / 3 + 4 / 3
- (7 % 4) / 2

.

All good?

.

- 1 / 10 = 0, because as we explained before, we get 0 with a remainder of 1, but we're not interested in the remainder in this case
- 5 % 3 = 2, since 3 goes into 5 once, and leaves a remainder of 2
- 2 / 3 + 4 / 3 = 1, In this case, 2 / 3 = 0 (integer math) and 4 / 3 = 1 (integer math)
- (7 % 4) / 2 = 1, 7 % 4 = 3, and 3 / 2 = 1

Now, looking back at our pseudocode, how can we convert it into real code?
```
1 | Starting Seconds = 3661
2 | Minutes = Starting Seconds / 60 (ignore the remainder)
3 | Seconds = The remainder of (Starting Seconds / 60)
4 | Hours = Minutes / 60 (ignore the remainder)
5 | Minutes = The remainder of (Minutes / 60)
6 | Output [Hours], [Minutes], [Seconds]
```

We have line numbers here just to make it easier to refer to.

There are some lines in our pseudocode that are already in our starter code. Can you spot them? Line 1 and line 6 of our pseudo code have already been written (woot free stuff!). Line 1 is written as `seconds = 3661;`. In this case, we're using the variable that we've named `seconds` to hold the Starting Seconds. Line 6 is written using the `System.out.printf` function. So, what we need to do next is to put our answers in the variables `hours`, `min` and `sec`, and the `printf` line will do the rest.

To start, let's substitute our pseudocode names for the actual variable names that we'll use:
```
1 | seconds = 3661
2 | min = seconds / 60 (ignore the remainder)
3 | sec = The remainder of (seconds / 60)
4 | hours = min / 60 (ignore the remainder)
5 | min = The remainder of (min / 60)
6 | Output [hours], [min], [sec]
```

This is looking better, but now we need to get rid of all of those pesky words. English is great and all, but the computer won't understand us well. Looking at our math code from earlier, how can we do division that ignores the remainder? How do we get the remainder?

Update the [starter code](https://www.ideone.com/f2g1K6) with your converted pseudocode and click the green button. Did it work? If it didn't, ask for help!

Once you have it working, change the value of `seconds` and see if it still gives the correct answer!

---------------------------------------------------------------
[Next: TBD >>]

[Back to Main](../../README.md)