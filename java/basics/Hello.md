## Say Hello!

**Objectives**: Learn the basics of code, and write a "Hello World" program

**Start Here**: [This code](https://www.ideone.com/lWuqvf)

**Process**:

1. Launch the starter code, and click on the text that says "fork"
    1. Let's take a look at the structure of this program. Right at the top, we have a line that says `class HelloWorld`. We'll ignore this for now (and we'll cover it in the section on Objects). You'll notice that on lines 2 and 7, there are braces (`{}`). All the code we'll write should be contained within these braces.
    2. Next, we see a line saying:

        ```public static void main (String[] args)```

        This is the starting point of this program. All Java programs will have one of these functions, called `main`. After this line, we again see braces/curly brackets `{ }` on different lines. Between these brackets is the **main body** of the code. This is because the are in the brackets that come after the name `main`.

2. Inside the **main body**, we're going to write the following line:

    ``` System.out.println(); ```

    Inside the `println` parantheses, write something that you want printed to the screen. Traditionally, we will write something like "Hello World". Make sure that whatever you want printed is surrounded by "double quotes". As an example, if I want to write "arr I'm a pirate", my code would look like:

    ``` System.out.println("arr I'm a pirate"); ```

3. Now that we have written our first code, let's see if it works! On the bottom write, there is a green button labeled "run". Click it!

    If everything went well, the box beneath the code will show the text you entered. If it didn't go well, you'll see some error messages under the label "compilation info". Make sure that you included a semicolon ";" at the end of your statement, and that you spelled and capitalized `System.out.println` correctly! Also make sure that you used double quotes ("") inside the parenthesis. If you had errors, click "edit" and fix them, then click the green button again.

    Woot! You printed some text! Play around with this by changing the text, or even adding more `System.out.println` lines!

[Next: Varied Variables >>](Variables.md)

[Back to Main](../../README.md)