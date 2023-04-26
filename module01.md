# Sprint 11 - Module 01
**Key Concepts**
- Creating React Tests
- Understanding Test Concepts
- Mocking Tests

**Essential Questions**
- How do you mock API calls with React's testing library?
- How do you test to see if a call is made?
- How do you select an element with the React testing library?

**Objectives**
- Test React components as the `props` change.
- Use mocks in web application tests.
- Test asynchronous API calls that are made in a component.

**Review: Why Test?**
- Having a comprehensive test suite allows us to trust the code.
- Safety net for future changes and refactoring (especially helpful for team collaboration).
- Bugs will immediately be surfaced in the future.
- Encourages modular, easy-to-understand code (tangled code is also often difficult to test).
- Helpful in quality control and deployment.
- Tests also act as a form of documentation and enforce best practices.
- Not testing is a bad idea. It's like taking out a hight-interest loan of technical debt.

**Review: AAA and Test Categories**
- AAA => Arrange, Act, Assert
- E2E => End to End Testing => Simulate Entire User Flow
- Integration Testing => Verify a Piece of the Application
- Unit Testing => Individual Functions or Components

## Module Notes
- *Mocks helps us simulate the behavior of real objects.*
- *Spies help us verify that the things we expect to be called are actually called.*
- *Naming convention for test files is `Component.test.js`*

## Module Examples
- *Assert a component has rendered...*
- ` test('renders without errors', () => {     `
- `   render(<App />)                          `
- ` })                                         `
- *Assert a function has been called...*
- ` test('function has been called', () => {   `
- `   expect(someFunction).toHaveBeenCalled(); `
- ` })                                         `
- *Use a fake version object for testing...*
- ` test('used fake data for testing', () => { `
- `   jest.mock(object, () => () => "abcde");  `
- ` })                                         `
- *Rerender a component with new data...*
- ` test('renders without errors', () => {     `
- `   render(<App />)                          `
- `   rerender(<App name={"Name"}/>)           `
- ` })                                         `


### Objective 1 - Test React Components as the Props Change
- There is a built-in method called `rerender()` that allows us to look at a component with new props easily.
- All `getBy` assertions return an error if they can't find the thing they're searching for (if a return is `null`).
- The assertion called `queryByRole` (or any `queryBy` assertion), will return null instead of an error. 
- This lets us query for something this isn't supposed to be on the DOM.
- It also allows us to use an assertion like `.toBeNull()` or `toBeFalsy()`, and then tests will start passing even when no content is rendered.

### Objective 2 - Use Mocks in Web Application Tests
- To isolate the behavior of the function, it's often desirable to replace the other objects with mocks that simulate the behavior of the real objects.
- Replacing objects is especially useful if the actual objects are impractical to incorporate into the unit test.
- Another use of mocks is as "spies" because they let us spy on the behavior of a function that is called by some other code.
- Mock functions can keep track of calls to the function and the parameters passed in those calls.
- Simpler mocks that implement only enough behavior to execute test code are sometimes called "stubs."

### Objective 3 - Test Asynchronous API Calls That Are Made in a Component
- An asynchronous test is a special kind of test that does not complete right away, as it needs to wait for the results of one or more asynchronous operations.
- The `waitFor` function from React testing library lets us tell the test that we need to wait for the async call to finish before continuing our assertions.
- As usual, we need to import the required libraries for testing.
- In addition to our normal libraries, we'll import `waitFor` to make our function run asynchronously.
- We'll import our `fetchData` as `mockFetchData` so that we don't have to wait for the actual call to be made.
- Remember, a mock allows us to isolate a function from its dependencies.
- We will create the mock outside of the test block to mock the `fetchData` async function.
- Inside the `test` block we will tell the mock function with what data it should resolve.
- Render the component, query for the necessary elements, and fire the onClick event with `userEvent`.
- We need to tell our test that it is going to handle an `async` function by adding async right after the test name string, and before the callback function.
- Basically this will tell the function that it's going to do an async operation.
- Tell the function which async operation it needs to wait for.
- Use the `await` keyword to tell the function we're awaiting for the async operation to finish.
- Use the `waitFor` function from RTL to wait for RTL to update the DOM so we can query for the dog images.
- Write an assertion in the `waitFor` functions callback function.
- Finally, we will make sure that the correct function was called by adding an extra assertion, `expect(mockFetchData).toHaveBeenCalledTimes(1);`.