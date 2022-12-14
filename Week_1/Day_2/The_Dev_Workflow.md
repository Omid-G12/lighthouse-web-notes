### The Dev Workflow

In this first lecture, we covered a lot!

* Curriculum Overview
* Approach to lectures
* Tools
* Git / Github
* Incremental developement

We used the sum demo to demonstrate the incremental development approach. The step-by-step process that breaks down as follow:

* State the hypothesis
* Verify the hypothesis
changes
* Rinse and repeat

For our sum problem, we broke down our problem into several steps without thinking about syntax. We used consol.log efficiently to validate our assumptions and see what is really happening.

Once our solution was obtained, we did refactor our code to make it more reusable and more readable.

``` javascript
// - Write a node program that takes in an unlimited number of command line arguments, goes through each and prints out the sum of them. If any argument is not a whole number, skip it. Do support negative numbers though. If any argument is not a number, output an error message. We need at least 2 arguments.

// extract command-line arguments
const args = process.argv.slice(2);

console.log('args:', args);

// Edge case: count the command line arguments and make sure there is at least 2 arguments

if (args.length < 2) {
  // ouput error message
  console.log('Error: please enter at least 2 arguments');
  // stop the execution
  // return;
  process.exit();
}

// go through each number and add them up

// c-style loop (for i=0; i<args.length;i++)
// for (let number of args) => more readable loop, no index



const sum = function (numbers) {
  // define an accumulator
  let total = 0;

  for (let nb of numbers) {
    // Edge case: are these numbers whole numbers => skip it
    // Math.ceil
    // Modulo %
    // Number isInteger

    const convertedNum = Number(nb);

    // Edge case =>if it's not a number => error message
    if (isNaN(convertedNum)) {
      console.log('Error: please enter only numbers');
      process.exit();
    }

    if (Number.isInteger(convertedNum)) {
      // typecast nb into a number (Number)
      total += convertedNum;
    }



    console.log('number:', nb, 'total:', total, 'type:', typeof convertedNum);
  }
  return total;
};

// prints ouput (sum)

console.log('Total:', sum(args));
```