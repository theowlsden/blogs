# TDD, a very non technical intro

Created: Apr 13, 2021 5:39 PM
Last Updated: Apr 13, 2021 11:10 PM
Tags: devops, beginner, tbd

As I am finishing my degree in ICT, I had to do an internship at an ICT company. Of course I am not interested in networking so I decided to apply at a local development company: Ictual N.V. After some talks to get to know the company and their products it was time to decide on an internship assignment. I choose the path of least resistance and decided to work on a web application, a portal for one of their products. Web dev is what I was doing at that time for a year so I was pretty comfortable with the choice of assignment. Then we started discussing their requirements for the assignment and they hit me with this: "This portal should be developed in accordance with the team's workflow, it should be developed according to Test Driven Development."

My jaw dropped.. WTF is that, I've heard about tests before but Test Driven Development? Never. So That was a challenge for that internship. I learned something new, and I hope that this high-level explanation will shine a light on TDD for you if like me you've never heard of the term.

## Test Driven Development, what is it exactly?

Well, TDD is a software development approach where you write test cases that explains your code before the actual code. For example, if you want to create a calculator, you will have to write tests for each functionality of the calculator (summation, subtraction, multiplication, division etc.). After writing those tests then you will be writing the minimal code to pass those tests. In case of summation, you will write the code to sum up two numbers.

Test Driven Development can be done in five basic steps:

- Write a test.
- Run the test and see it fails.
- Write the simplest code to satisfy the expectation of the test.
- Run test again and see if the written code passes the test.
  <br> If it passes refactor the
  code and if not change the code.
- Repeat

When talking about TDD, we can talk about two different levels of tests:

- Acceptance TDD (ATDD) - you write a single acceptance test that fulfills the
  behavioral specification of your project that describe how the system should
  function. Behavioral specifications describe how the different classes and modules in your application with each other. This is also known as Behavior Driven Development. The aim of ATDD is
  to specify the requirements of your project. Most times this is achieved by working with User Stories and Use Cases.
- Developer TDD (DTDD) - you write a single test that focuses on every small
  functionality of your project. DTDD is simply called TDD.

Now that we have an idea of what TDD is, the next logical question is: WTF is tests anyways?

## Tests

For every time that the word "test" was mentioned, let's take a shot of... water 🥤, we should be sober for the next part.

Tests are assertions that you write about a functionality of your software. "It should sum up two numbers". In a test you describe a functionality and what you expect from it when it is executed. For example:
description: "The calculator should sum up two numbers", expectation: "2 + 2 = 4". That just now was a Unit Test. Unit tests allow you to set description and expectation of one specific logic in your code.

The general rule of thumb is that for every Unit Test, you write a function. This simplifies your code and makes it easier to debug and reuse in the future.

In software development there are a ton of different forms of software testing, but the most important tests you will be writing as a developer are Unit Tests and Acceptance tests. For you front-end developers end-to-end (e2e) testing will be pretty important. In e2e you will be testing the UX of your application. How all the components flow and work with each other.

### Important best practices when creating tests

- Use descriptive names for test functions, by the name of the function you should
  know what you are testing.
- Separate testing code from implementation code but keep testing classes in the
  same directory as the implementation code.
- Limit the number of assertions in a test, write more test functions if necessary. If
  you need to test multiple assertions (expectations that the code really executes
  what it is intended to execute) it is recommended to create a test for each one of
  them. This makes debugging easier and the testing code cleaner to read.
- Write the simplest code that would pass the test. Separate your logic into
  different and write the simples code to pass each test at a time. At the end of the
  test suite, your code will be executing the complex logic because each individual
  section works as it should.

Now, let's write a test for our summation example. I will write this in the format of the tool Jasmine. Jasmine is one of many testing tools developed for the language JavaScript. Jasmine comes preinstalled in your Angular project, which is what I used for my internship. While depending on your programming language and tool the syntax may very, the general gist of how to write a test is the same.

```javascript
// import dependencies for testing
import { ComponentFixture, TestBed } from "@angular/core/testing";
import { ComponentName } from "./component-name.component";
describe("CalculatorComponent", () => {
  // create component instance
  let component: ComponentName;
  let fixture: ComponentFixture<ComponentName>;
  beforeEach(async () => {
    // import and declare dependencies for the component
    await TestBed.configureTestingModule({
      declarations: [ComponentName],
    }).compileComponents();
  });
  beforeEach(() => {
    // initialize component instance
    fixture = TestBed.createComponent(ComponentName);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });
  // test that should be run on the component code
  it("should calculate a sum", () => {
      const expectation = 4;

    expect(component.sumNumber(2,2)).toEqual(expectation);
  });
});
```
Again, the code above is specifically for Angular. Your milage may vary but that right there, is a working example of a test to assert that the function called sumNumber returns the sum of 2 + 2.

You will first import the tools you need to test your code and the piece of code you want to test. Then you start writing your test suite. Your test suite is all the tests you will execute for a specific part of your application (software 🤷🏿‍♀️). Your test suite lives in a **describe** function. The first parameter will describe the part of your application that you are testing, the second part will describe the function that will contain your tests.

 Then you write the **beforeEach**. In your beforeEach function you write what should happen, well, before each test case. Here you create a new instance of your piece of code and pull in every dependency for your tests. 

 After that comes the fun part, the tests. The tests have an almost human language type of syntax. All your tests will be in the form of an **it** function. The first parameter will be the description of your test, what exactly are you testing? What should it (your code) do? The second parameter contains the function that will execute your code and run it against your expectation. In that function you need to set all that is necessary for the logic to function properly. In our summation case, call the function with the two numbers we want to sum.

 > Remember, the first time you are running your tests, they should fail. The test should be written before the code.

With your tests in place, go on and start developing the best application you can. Using Test Driven Development will encourage you to think critically about your code and allow you to write cleaner code. The benefits of cleaner code is endless. Your code will be easier to understand, easier to reuse, easier to add new developers to the project and easier to debug among other things.

I hope that you learned something new from this post and that you will consider using this development approach for your next million dollar application idea.🤙🏿



