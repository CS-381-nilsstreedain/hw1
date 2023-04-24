# Homework 1
## Select a programming language you have not used (NOT Haskell or Prolog). Give a brief history of this language. Who developed the language? When? Where?
I have chosen the Rust programming language for this assignment. Rust was initially designed by Graydon Hoare as a personal project in 2006. Mozilla began sponsoring the project in 2009, and in 2010, the project was officially announced. Rust's first stable release, Rust 1.0, was launched on May 15, 2015.

## Give a description of the language. What is its paradigm(s)? How is it categorized? Describe some of the features of the language. What is typing method/discipline?
Rust is a systems programming language that emphasizes safety, concurrency, and performance. It is categorized as a multi-paradigm language, supporting imperative, functional, and concurrent programming styles. Some of the notable features of Rust include its ownership system, pattern matching, type inference, and memory safety guarantees. Rust uses static typing and employs a strong, statically-typed discipline.

## Is the language compiled or interpreted? On what platforms is the language available? Is the language standardized? Are there different implementations?
Rust is a compiled language. The primary compiler is rustc, which uses LLVM as its back end. Rust is available on various platforms, including Windows, macOS, and Linux. The language is standardized and governed by the Rust project, which is run by the Rust team and the community. The official implementation of Rust is the Rust compiler (rustc), and alternative implementations, like mrustc, are also available.

## Give examples of at least two control structures in the language (ie. for-loop or if-statement). Explain.
Here are two control structures in Rust:

### if statement:
This control structure checks if x is greater than 0. If true, it prints "x is positive", otherwise, it prints "x is negative."
```rust
let x = 5;

if x > 0 {
	println!("x is positive");
} else {
	println!("x is negative");
}
```

### forloop:
This control structure iterates over the range 1 to 4 (excluding 5), printing the value of i at each step.
```rust
for i in 1..5 {
	println!("i is: {}", i);
}
```

## To complete questions 6- 8 you will need to find an online complier/ interpreter to run code in your language, for example https:// onecompiler.com/ . Alternatively you can install the software or use the school’s server. What will you be using?
I will be using the [Rust Playground](https://play.rust-lang.org/) to compile and run code in Rust for this assignment.

## Write a “Hello World” program written in the language. Describe how it works. Provide a screenshot of the execution of the program.
```rust
fn main() {
	println!("Hello, World!");
}
```
This program defines a **main** function, which is the entry point of the Rust program. The **println!** macro is used to print the "Hello, World!" string to the console. Here is a screenshot of the execution:

![page3image30977968](https://user-images.githubusercontent.com/25465133/233872802-87b2f71c-0ee7-43a2-b3f2-87b06909bb25.png)

## Write a program to compute the first n Fibonacci numbers where the user is prompted for n (if possible). Describe how the code works. Is the program iterative or recursive? Provide a screenshot of the execution of the program.
```rust
use std::io;
fn main() {
	let mut n = String::new();
	println!("Enter a positive integer:");
	io::stdin()
		.read_line(&mut n)
		.expect("Failed to read input");
	let n: u32 = match n.trim().parse() {
		Ok(num) => num,
		Err(_) => {
			println!("Invalid input, using default value 10.");
			10
		}
	};

	let mut a = 0;
	let mut b = 1;

	for _ in 0..n {
		println!("{}", a);
		let temp = a;
		a = b;
		b = temp + b;
	}
}
```
This program reads an integer **n** from the user, then iteratively computes the first **n** Fibonacci numbers. It uses a loop to perform the calculations and print the Fibonacci numbers. The program is iterative. Here is a screenshot of the execution:

![page5image32007472](https://user-images.githubusercontent.com/25465133/233872963-018277f5-9a04-45ef-b1fd-73c17e0f354a.png)

## Write a program to sort a list of integers. You can use any sorting algorithm, but do not use library functions. Describe how the code works. Provide a screenshot of the execution of the program.
```rust
fn bubble_sort(arr: &mut [i32]) {
	let len = arr.len();
	for i in 0..len {
		for j in 0..len - i - 1 {
			if arr[j] > arr[j + 1] {
				arr.swap(j, j + 1);
			}
		}
	}
}

fn main() {
	let mut nums = [5, 3, 8, 1, 6, 9, 2, 7, 4];
	println!("Before sorting: {:?}", nums);
	bubble_sort(&mut nums);
	println!("After sorting: {:?}", nums);
}
```
This program defines a function **bubble_sort** that takes a mutable reference to an array of i32 integers. The function iterates through the array, comparing adjacent elements. If an element is greater than the next one, the elements are swapped. This process is repeated until the entire array is sorted.

In the **main** function, we create an array of integers called **nums** and print it before and after sorting. We call the **bubble_sort** function with a mutable reference to **nums** to sort the array in-place. Here is a screenshot of the execution:

![page7image30984272](https://user-images.githubusercontent.com/25465133/233873142-21e41875-dca9-4f97-9097-9b29973404aa.png)

## List at least three references you used for this assignment. Include any sites that you used to obtain code.
Here are three references I used for this assignment:
1. [Official Documentation](https://doc.rust-lang.org/book/)
2. [Rust Playground](https://play.rust-lang.org/)
3. [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)

The code provided in this assignment was primarily based on my knowledge and the official Rust documentation. However, these resources were also helpful in confirming the syntax and understanding certain aspects of the Rust programming language.
       
## Would you like to learn more about this language? Would anticipate using this language in the future? Explain.
I would definitely like to learn more about Rust. Its focus on safety, concurrency, and performance makes it a valuable addition to my programming skill set. With the increasing importance of safe and efficient systems programming, Rust is becoming a popular choice for developing system utilities, operating systems, and web applications. Moreover, Rust has been consistently ranked as one of the most loved programming languages in the Stack Overflow Developer Survey, indicating a strong and growing community behind it. I anticipate using Rust in the future for projects where safety and performance are crucial, such as embedded systems, web development with WebAssembly, or even game development. Its strong safety guarantees and modern syntax make it an appealing choice for both professional and personal projects.
