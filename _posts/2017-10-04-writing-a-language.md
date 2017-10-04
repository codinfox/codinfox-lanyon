---
layout: post
title: I'm Writing a Programming Language
---

It's called [Willow](http://github.com/michaelkent94/willow).

My goal is to write a language that I would enjoy using for every day programming.
My hope is that other people will also.

At this point, the syntax of Willow is still actively changing, but currently it looks something like this:

```willow
// No main function, anything on the toplevel is executed
:number = {fib n: 10}
{print "The 10th fibonacci number is \(number)"}

// Define a new function called fib
{:fib n: Int -> Int
    {? n < 2
        -> n
     ?
        -> {fib n: n - 1} + {fib n: n - 2}
    }
}

// Now print the first 10
{@ :i <- [1...10]
    {print "\({fib n: i})"}
}
```

I want the focus to be taken away from long, verbose keywords like `public static void` or `public private(set) lazy var` 
and instead, put it on what the programmer writes. So that's why Willow will make heavy use of simple, understandable symbols.
For instance: in the example above, take a look at the 'if' statement. It uses a `?` to denote a conditional. It's simply
asking a question.

The `:` symbol is used for definitions. A variable is defined like `:number`. A function is defined like `{:fib ... }`.

The `@` symbol looks kind of like a loop so it's used for loops. The example above shows a 'foreach' style loop but
'while' style loops will also be supported by starting with `@?` instead of just `@` (i.e. a conditional loop, see how it
makes sense?).

I am *very* excited about this project. However, I have a bad habit of starting projects and letting them slide away because
I don't have time to work on them, or I lose interest, or they get hard. I know this will get hard. I won't always have time
to work on it. I'll probably lose interest. But nonetheless, here we go.
