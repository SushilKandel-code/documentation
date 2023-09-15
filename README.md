# COSC360/COSC560 Advanced Web Programming Assignment 5

**TOPIC COVERED**
- [COSC360/COSC550 Advanced Web Programming Assignment 5](#cosc360/cosc560-advanced-web-programming-assignment-5)
- [Take an online course](#take-an-online-course)
- [What is Typescript?](#what-is-typescript?)
- [Why Typescript is used in React?](#why-typescript-is-used-in-React?)
- [Getting Started with Typescript React](#getting-started-with-typescript-react)
- [Insight summary of skills that I learned from typescript react online course:](#insight-summary-of-skills-that-i-learned-from-typescript-react-online-course)
- [Complete an official online tutorial](#complete-an-official-online-tutorial)
- [Insight summary of skills that I learned from completing an official online tutorial](#insight-summary-of-skills-that-i-learned-from-completing-an-official-online-tutorial)
- [Programming Challange](#programming-challange)
 - [Programming challange 1(Source: Project Euler problem 1)](#programming-challange-1source-project-euler-problem-1)
 - [Programming Challange 2 (Source: Project Euler problem 7)](#programming-challange-2-source-project-euler-problem-7)
 - [Programming Challange 3 (Source: Project Euler problem 4)](#programming-challange-3-source-project-euler-problem-4)

## Take an online course
### What is typescript?
TypeScript is an open-source programming language developed and maintained by Microsoft. It is a statically-typed superset of JavaScript, which means that it builds upon JavaScript by adding optional static typing. TypeScript code is designed to be compiled into plain JavaScript that can run in any browser or JavaScript runtime

### Why Typescripy is used in React?
TypeScript enhances the development experience and code quality when building React applications, making it a popular choice for many developers and teams. The use of Typescript can help you to create more robust React cocebase with fewer errors.

### Getting Started with Typescript React
You can use the Typescript template for creating a typescript project:
npx react-native init MyApp --template react-native-template-typescript

### Insight summary of skills that I learned from typescript react online course:
I gained valuable insights into correctly defining the type of 'useRef' in React. It's essential to initialize 'useRef' with 'null' as the default value since it can only hold either a 'null' or the actual DOM element reference. Additionally, I learned the significance of using 'useLayoutEffect' when making changes to the DOM reference object and the importance of adding conditionals to ensure it's not null. I acquired a deep understanding of how to effectively integrate Typescript, React, and Redux, including the utilization of Redux Middleware. I learned how to craft highly reuseable React components and optimize performance by harnessing Web Assembl1y technology in our application.

## Complete an official online tutorial
### Insight summary of skills that I learned from completing an official online tutorial:
From this tutorial, I gained a clear understanding of how data flows within a React application, particulary when passing props from parent components to child components. I also learned the correct usage of state and porps to control the game oand achieve the desired outcomes. From this tutorial, I developed a solid grasp of how the information flows within the React application, especially when it involes the transmission of props from the parent components to their child counterparts.

## Programming Challange

### Programming challenge 1 (Source: Project Euler Problem 1)

Problem 1
Find the sum of first 1000 prime numbers
```
def is_prime(num):
    if num <= 1:
        return False
    if num <= 3:
        return True
    if num % 2 == 0 or num % 3 == 0:
        return False
    i = 5
    while i * i <= num:
        if num % i == 0 or num % (i + 2) == 0:
            return False
        i += 6
    return True

def sum_of_first_n_primes(n):
    sum_primes = 0
    count = 0
    num = 2  # Start with the first prime number
    while count < n:
        if is_prime(num):
            sum_primes += num
            count += 1
        num += 1
    return sum_primes

n = 1000
result = sum_of_first_n_primes(n)
print(f"The sum of the first {n} prime numbers is: {result}")
```

Problem 2
Find the sum of first 1000 even numbers
```
function sumOfFirstNEvenNumbers(n: number): number {
    let sum = 0;
    let count = 0;
    let num = 2; // Start with the first even number

    while (count < n) {
        sum += num;
        num += 2; // Increment by 2 to get the next even number
        count++;
    }

    return sum;
}

const n = 1000;
const result = sumOfFirstNEvenNumbers(n);
console.log(`The sum of the first ${n} even numbers is: ${result}`);
```

Problem 3
Find the sum of first 1000 odd numbers
```
function sumOfFirstNOddNumbers(n: number): number {
    let sum = 0;
    let count = 0;
    let num = 1; // Start with the first odd number

    while (count < n) {
        sum += num;
        num += 2; // Increment by 2 to get the next odd number
        count++;
    }

    return sum;
}

const n = 1000;
const result = sumOfFirstNOddNumbers(n);
console.log(`The sum of the first ${n} odd numbers is: ${result}`);
```

Problem 4
Find the sum of first 1000 numbers divisible by 2 and 2 in react typecript
```
import React, { Component } from 'react';

class SumDivisibleBy2And3 extends Component {
  calculateSum = () => {
    let sum = 0;
    let count = 0;
    let num = 1;

    while (count < 1000) {
      if (num % 2 === 0 && num % 3 === 0) {
        sum += num;
        count++;
      }
      num++;
    }

    return sum;
  };

  render() {
    const sum = this.calculateSum();

    return (
      <div>
        <p>The sum of the first 1000 numbers divisible by 2 and 3 is: {sum}</p>
      </div>
    );
  }
}

export default SumDivisibleBy2And3;

```

Problem 5
Making Login form with React typescript
```
import React, { Component, FormEvent } from 'react';

interface LoginState {
  username: string;
  password: string;
}

class LoginForm extends Component<{}, LoginState> {
  constructor(props: {}) {
    super(props);
    this.state = {
      username: '',
      password: '',
    };
  }

  handleInputChange = (event: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = event.target;
    this.setState({ [name]: value } as Pick<LoginState, keyof LoginState>);
  };

  handleSubmit = (event: FormEvent) => {
    event.preventDefault();
    // You can add your login logic here
    console.log('Submitted with username:', this.state.username);
  };

  render() {
    return (
      <div>
        <h2>Login</h2>
        <form onSubmit={this.handleSubmit}>
          <div>
            <label htmlFor="username">Username:</label>
            <input
              type="text"
              id="username"
              name="username"
              value={this.state.username}
              onChange={this.handleInputChange}
              required
            />
          </div>
          <div>
            <label htmlFor="password">Password:</label>
            <input
              type="password"
              id="password"
              name="password"
              value={this.state.password}
              onChange={this.handleInputChange}
              required
            />
          </div>
          <div>
            <button type="submit">Login</button>
          </div>
        </form>
      </div>
    );
  }
}

export default LoginForm;
```





