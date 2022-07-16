> The most cliche start to learning any programming language: the `hello` program.

The `hello` program has a simple purpose: to print the text _"hello, world!"_ onto the console. In _C++_, the `hello` program looks something like this:

<p align='right'><code>hello_world.cpp</code></p>
```cpp
#include <iostream>

int main() {
	std::cout << "hello, world!\n";
	return 0;
}
```

You may also find a more common yet worse variation of the above program used by many professors and websites teaching _C++_:

<p align='right'><code>worse_hello_world.cpp</code></p>
```cpp
#include <iostream>

using namespace std;

int main() {
	cout << "hello, world!" << endl;
	return 0;
} 
```


Now that we have defined what we mean by the `hello` program, let's break it down to understand each statement.

### Breaking Down the `hello` Program

Let's start with the program: `worse_hello_world.cpp`. Once that is done, we'll discuss what's wrong with it and how/why `hello_world.cpp` is better.

#### The `#include` statement

The first line in the program is the `#include` line:
```cpp
#include <iostream>
```
There is actually a lot more to the `#include` line, like the concept of the _preprocessor_ and _header files_. Since we're just getting started, and because the mentioned topics are quite on the intermediate level, we'll not get into them just yet. Instead, to understand what the `#include` statement does, you can simply think of it as a line that allows your code access to features of _C++_ that deal with any kind of _input/output_. 

Whether it is taking some kind of input from the user, or displaying a message (which is technically what we're trying to do with the `hello` program), you'll most probably be using the `iostream` header provided in the _C++ standard library_.

The _C++ standard library_ is a collection of features which come "_pre-packaged_" with the C++ programming language. They were made and included by the creators of the langauge.

For the `hello` program, we'll specifically be making use of the `cout` functionality from the `iostream` header of the _standard library_. But before we discuss that, let's have a look at the next line...

### The `using namespace std` statement

The next line: `using namespace std;` has a lot to it, much that pertains to advanced concepts like _namespaces_. Since that's a topic for later, let's just say that this line asks the compiler to explicitly use something called the _standard namespace_ which too, allows it access to functionality from the _standard library_.

Please note that it is usually not recommended, and often considered bad code practice, to use this line. Especially in header files, since it can cause something called _namespace poisoning_ and _namespace collisions_. This is one of the reasons why the `hello_world.cpp` program is better than `worse_hello_world.cpp`. If you wish to read more on it, I would recommend [[Bibliography#^bc8415|this]] thread from _[stackoverflow.com](https://stackoverflow.com)_ which discusses exactly this.


### The `main` function

The next line in `worse_hello_world.cpp` is the line:
```cpp
int main() { 
```
Well, just like the previous statement, there's a lot more to this line than meets the eye. We need not worry ourselves with what a _function_ is just yet. As every tutorial will tell you, this line is used by the _C++ compiler_ to specify the **entry point** to a program, that is, the `main` function acts as the point of beginning of the actual program. The compiler will execute whatever instructions we give it as long as they are correct and reside inside the `main` function.

The `{` at the end of the statement signifies the start of a _code block_. For now, you can think of it as a box within which instructions can be stored (written) and they'll be executed in whatever order specified. The `}` at the end of the `hello` program specifies the end of this code block. 
```cpp
int main() { // beginning of program
	// ...
	// program instructions
	// ...
} // end of program
```
So whatever is within those two `{` and `}` will be executed by the compiler. This also brings us to a very important subsection: _comments_

Notice how in the above code block there's several `//` characters that are followed by some text? Those are _comments_ . These _comments_ are lines that are skipped/ignored by the compiler, so whenever you _comment something out_, you specify to the compiler that it is to skip that particular line:
```cpp
// This is a single line comment.
// The compiler will ignore these lines.

/*
	This is a multi-line comment.
	whatever is within these will also be ignored by the compiler...
*/
```
As you can see in the above code block, multi-line comments can be made using `/*` (to begin the comment) and `*/` (to end it).

This brings us onto the next line...

### The `cout` statement

The line in question is:
```cpp
cout << "hello, world!" << endl;
```
As you can probably guess, this is the line which does the _printing to console_ bit for our `hello` program. The `cout` (short for  _console output_) instruction is a functionality from the `iostream` header that we included using the `#include` statement earlier, and so is `endl` (short for _end line_). The _[[Appendix#^2bf2d3|syntax]]_ for the `cout` statement/instruction is as follows:
```cpp
cout << stuff_to_print ...;
```
In the case of the `hello` program, the `stuff_to_print` is replaced by the string: `"hello, world!"`, followed by `endl`. Now, the use of `endl` is usually not recommended, and the reason is quite confusing to understand if you're new to programming. So if you want to read up on it, I'd recommend reading [[Bibliography#^62d397|this]] stackoverflow thread. A short and sweet explaination is that 

> The difference is that [`std::endl`](http://en.cppreference.com/w/cpp/io/manip/endl) flushes the output buffer, and `'\n'` doesn't. If you don't want the buffer flushed frequently, use `'\n'`. If you do (for example, if you want to get all the output, and the program is unstable), use `std::endl`.

Generally, you don't really need to flush the output buffer unless you actually have to. So it's not generally recommended that you flush it.

In any case, if you're confused as to what _"flushing the output buffer"_ means, don't worry for now, you can learn about it as you progress through programming as a whole. Specifically, when you study **File I/O**.

This brings us to the last instruction in the `main` function...

### The `return` statement

The final statement, the `return` statement marks the end of the `main` function, and thus our program. Just as the `main` function is the entry point of the program, the `return` statement is the _exiting point_ for the main program (and as you'll learn later, for any kind of function). 

The `return` statement actually makes the function result to something. As the name suggests, it will make the function _return_ something. For now, think of it as the program giving out a result for the compiler. `return 0;` makes the program return a value of `0` which refers to a _successful program execution_. The value returned is also known as an **exit status**. 

An _exit status_ of `1` means that the program was unsuccessful in whatever it did. There's many more exit status codes available, which mean tons of different things. You can read more about them on the [manpage of `exit`](https://www.man7.org/linux/man-pages/man3/exit.3.html) or _[[Bibliography#^846828|here]]_. As to how we use and interpret them in code, we'll be discussing that when we cover more intermediate topics.

## A Brief Study of `hello_world.cpp`

The program `hello_world.cpp` is better than `worse_hello_world.cpp` (yes it's quite obvious from the names). Although some may argue that the former is actually more complicated, or that it simply does not matter for this example. However, the people who say this do not take into account that whatever is taught from the beginning, becomes practice. Writing good, secure and readable code is a very important aspect of programming. 

The first noticable difference between `hello_world.cpp` and `worse_hello_world.cpp` is the lack of the `using namespace std;` statement. As explained under the section: [[#The using namespace std statement]] of this text, the use of said statement is not recommended, and often considered _bad code practice_, and thus should be avoided unless necessary.

The second difference between the two is the `cout` statement. This difference arises due to the lack of the `using namespace std;` statement. Since we're not using it, we'll need to tell the compiler _exactly_ what we mean by `cout`. The `std::cout`, for now, can be understood as telling the compiler: _I want to use the `cout` defined in `std`_. Here, `std` refers to the _standard library namespace_. Thus, when we write `std::cout`, we essentially eliminate the need for the `using namespace std;` statement.

The third and minor difference is the lack of `endl` in `hello_world.cpp`. The difference is already discussed under the section: [[#The cout statement]]. The key point to note is that unless you need to _flush your output buffer_, it's not recommended that you use `endl`, and so, we can use a special character sequence, called an _[[Appendix#^ab6bab|escape sequence]]_, which in this case, is `\n` (which represents a _new line_).


> This marks an end to our venture of breaking down the `hello` program. I hope you learned something new and found this helpful. :D