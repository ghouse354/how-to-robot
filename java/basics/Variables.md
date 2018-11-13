## Varied Variables!

[<< Previous: Say Hello](Hello.md)

------------------------------------------------------------------

**Objectives**: Learn what variables are, and how to write code with them

**Process**:

Previously, we learned how to write code to print text to the screen. That's good, but everything you want to change something, you'll have to rewrite your code. The code we wrote also wasn't very dynamic or interesting, so now, let's write some code that does stuff that's a little more interesting.

Imagine that we want to write some code that converted seconds into hours, minutes and seconds. On a piece of paper - writing every step - figure out how many hours:minutes:seconds (H:M:S) there are in 3661 seconds.

.

Really, do it by hand, on paper.

.

Have an answer?

.

You should have gotten 1 hour, 1 minute and 1 second. Now, what if I had asked for how many H:M:S there are in 3667?

Let's write a generic way to solve this problem, so that we can solve it for any number of seconds.

There are multiple ways to start (and you may have already used one of these methods when doing it by hand) - maybe we can convert the seconds to minutes first, and then convert minutes to hours. Or maybe we convert to hours first and figure out how many minutes are left. There is no right or wrong way to solve this problem, as long as it works.

For the sake of this tutorial, let's use the method that converts from seconds to minutes to hours.

We'll first convert seconds to minutes by dividing the seconds by 60. For 3661 seconds, the division is 61 minutes with 1 second left over.

Next, we'll divide the minutes by 60, so that we can get hours. 61 minutes is 1 hour with 1 minute left over.

At this point, we know that 3661 seconds = 1 hour, 1 minute, 1 second.

Let's write the steps in math-ish:
```
Starting Seconds = 3661

Minutes = Starting Seconds / 60 (ignore the remainder)

Seconds = The remainder of (Starting Seconds / 60)

Hours = Minutes / 60 (ignore the remainder)

Minutes = The remainder of (Minutes / 60)

___ [starting seconds] is ___ [Hours] hours, ___ [Minutes] minutes and ___ [Seconds] seconds.
```

If you're confused, ask for help!

Now that we've broken down how to solve the problem generically, let's try to code it!. Here's some [starter code](https://www.ideone.com/f2g1K6).

In the starter code, we see the main function and the main body, like our last example. However, we also see something new:

``` java
int seconds;
int hour;
int min;
int sec;

seconds = 3661;
```

Here, we are declaring **variables**. What are variables? Glad you asked! **Variables** are places in your code where you can store *values* (e.g. numbers). Different types of variables can store different types of things. If we want to store whole numbers (e.g. -2, -1, 0, 1, 2, etc) we will make an `int` or **Integer**. If we want to hold a number that's not a whole number (e.g. 3.14, 0.99, -16.5, etc), we would use a `double`. There are more *types* than just integers and doubles, but we'll cover those later.

In the line `int seconds;`, we are telling the computer that we want a place to put whole numbers (hence the `int` at the beginning), and we are going to call it "seconds". The following lines are creating more *integer* variables with different names.

In the line `seconds = 3661;`, we are *assigning* a value to `seconds` - In this case, we are assigning the value of 3661. So now, `seconds` equals 3661 until we assign it a new value. When we assign values to variables, we always put the variables on the left side of the equal sign, and the new value on the right side. To quickly demonstrate:

``` java
int a;
int b;

a = 4;
// a is now assigned the value of 4
b = 6;
// b is not assigned the value of 6
a = b;
```

We read code from top to bottom, and unlike in algebra, the value of the variable can be changed. What do you think `a` and `b` are at the end of the code? If you thought that `a` and `b` are not equal, or that they both equal 4 - sorry, you didn't get it. But if you thought that `a` and `b` both equaled 6, then good job!

`a` equals 6 because assigning values *always* goes from the right to the left. The variable on the left of the equal sign is the variable changing its value. Given this, if you try to write `6 = a`, the computer will get confused - you cannot reassign the value of 6. 6 is always 6.

Let's play around with some math in code! Open this [math code](https://www.ideone.com/kESOfT) and run it. See what happens! Try changing numbers, can you figure out what is happening?

Try to find three differences (in both the printed lines and the code) between the integers and doubles.

One thing you may have noticed is that division behaves weird with integers - Why would 4 divided by 15 return 0? Why is 15 divided by 4 only 3? The reason is because we are doing *integer math*. Integer math is very similar to 3rd grade math class. Remember when you first learned about division, and we had these things called remainders?

![IMAGE](https://dj1hlxw0wr920.cloudfront.net/userfiles/wyzfiles/b410fcc6-7a7b-45a0-81b9-354423866db9.gif)

With integer division, we don't care about the remainder, we only care about the number before the remainder. So, with 128 / 5, we only care about the 25, and throw out/ignore the remainder 3. By the same logic, 1 / 10 will be 0 with integer division - The answer is 0 remainder 1.

But what if we *wanted* the remainder? That's where the percent sign (%) comes in. We call this operation *modulus* or *mod*. If I wanted the remainder of 10 / 4, I would write `c = 10 % 4` or say "c equals 10 mod 4". After that line of code, what would `c` equal? That's right, it would equal 2.

To make sure we're good on this, write down the answers to the following equations (following integer math rules):
- 1 / 10
- 5 % 3
- 2 / 3 + 4 / 3
- (7 % 4) / 2

.

Did you write them down?

.

Really?

.

Fine.

.

- 1 / 10 = 0, because 10 goes into 1 no times (0). Integer division, we don't care about the remainder here
- 5 % 3 = 2. Here we only care about the remainder. 3 goes into 5 one time with a remainder of 2.
- 2 / 3 + 4 / 3 = 1 - Integer division! 2 / 3 = 0, and 4 / 3 = 1!
- (7 % 4) / 2 = 1 - This was more about combining concepts. 7 % 4 = 3, and 3 / 2 = 1

So, looking back at our math-ish, how can we convert it to code?
```
1 | Starting Seconds = 3661
2 | Minutes = Starting Seconds / 60 (ignore the remainder)
3 | Seconds = The remainder of (Starting Seconds / 60)
4 | Hours = Minutes / 60 (ignore the remainder)
5 | Minutes = The remainder of (Minutes / 60)
6 | ___ [starting seconds] is ___ [Hours] hours, ___ [Minutes] minutes, and ___ [Seconds] seconds
```
We have line numbers there to make the math-ish "code" easier to refer to.

In the starter code, we already have line 1 and line 6 written (woohoo, free stuff!). Line 1 is written as `seconds = 3661;`. We're using the variable `seconds` to hold the Starting Seconds. Line 6 is written using the `System.out.printf` function. We'll put our answers in the variables `hours`, `min` and `sec`, and the `System.out.printf` line will print out their values. So, we only need to write lines 2 to 5.

The first thing we should do is the substitute our math-ish names for the variable names:
```
min = seconds / 60 (ignroe the remainder)
sec = The remainder of (seconds / 60)
hour = min / 60 (ignore the remainder)
min = The remainder of (min / 60)
```
Now we need to get rid of all those words! English is great and all, but the computer won't understand us. Looking at our math code from earlier, how do we do division that ignores the remainder? How do we get the remainder?

Update the [starter code](https://www.ideone.com/f2g1K6) with your converted math-ish and click the green button. Did it work? If it didn't, ask for help!

Once you have it working, change the value of `seconds` and see if it still gives the correct answer!

---------------------------------------------------------------
[Next: TBD >>]

[Back to Main](../../README.md)