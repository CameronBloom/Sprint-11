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

## Notes
- *Mocks helps us simulate the behavior of real objects.*
- *Spies help us verify that the things we expect to be called are actually called.*
- *Naming convention for test files is `Component.test.js`*

## Examples
- ` test('renders without errors', () => { `
- `   render(<App />)                      `
- ` })                                     `

### Objective 1 - Test React Components as the Props Change
- There is a built-in method called `rerender()` that allows us to look at a component with new props easily.
- All `getBy` assertions return an error if they can't find the thing they're searching for (if a return is `null`).
- The assertion called `queryByRole` (or any `queryBy` assertion), will return null instead of an error. 
- This lets us query for something this isn't supposed to be on the DOM.
- It also allows us to use an assertion like `.toBeNull()` or `toBeFalsy()`, and then tests will start passing even when no content is rendered.

### Objective 2 - Use Mocks in Web Application Tests
