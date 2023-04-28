# Sprint 11 - Module 02
**Key Concepts**
- Authentication and Authorization
- Passing Token into Headers
- Blocking Routes

**Essential Questions**
- How do you pass an authorization header with axios?
- How do you create protected routes?
- How do you save a token from the backend to use for authorization?

**Objectives**
- Handle authentication with tokens in a React app.
- Implement protected routes using an authentication token and redirect.

**Review: JSON Web Tokens and Auth**
- The client app makes a request to the login endpoint on a web server, sending the username and password.
- If successful, the server responds with a token, which the client app saves locally in the browser (via localStorage, cookies, etc.).

**Review: Local Storage**
- Local storage provides a very straightforward way of saving key/value pairs locally in the browser.
- `localStorage.setItem('key', 'value');  // sets pair     `
- `localStorage.getItem('key');           // returns value `
- `localStorage.removeItem('key');        // removes pair  `
- `localStorage.clear();                  // removes all   `

**Review: Security Concerns**
- We use localStorage because it is convenient.
- Don't use localStorage to actually implement auth.
- Using local storage invites cross-scripting attacks.

**Review: API (HTTP and REST)**
- HTTP (axios) | CRUD (rest) | Description                         | Happy Path
- ===============================================================================================
- get          | read        | Read a representation of a resource | 200 (OK)
- post         | create      | Create new resources                | 201 (created)
- put          | update      | Update a resource                   | 200 (OK) or 201 (created)
- delete       | delete      | Delete a resource                   | 200 (OK) or 204 (no content)
- 
- Errors
- ===============================================================================================
- Error: 400 Bad Request - Sent invalid JSON or the syntax/context is incorrect
- Error: 401 Unauthorized - Access credentials were missing or invalid
- Error: 403 Forbidden - Access credentials are valid but not authorized to access the resource
- Error: 404 Not Found - Request is valid, but the resource does not exist or is outside scope

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


### Objective 1 - Handle Authentication With Tokens in a React App
- 

### Objective 2 - Implement Protected Routes Using an Authentication Token and Redirect
-