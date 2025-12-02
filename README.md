# Test_Cypress_demo

🌲 Cypress
Documentation | API reference

Cypress is a next generation front end testing tool built for the modern web. It addresses the key pain points developers and QA engineers face when testing modern applications. Cypress is fast, easy, and reliable testing for anything that runs in a browser.

|          | Linux | macOS | Windows |
|   :---   | :---: | :---: | :---:   |
| Chromium <!-- GEN:chromium-version -->143.0.7499.4<!-- GEN:stop --> | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| Firefox <!-- GEN:webkit-version -->26.0<!-- GEN:stop --> | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| Edge <!-- GEN:firefox-version -->144.0.2<!-- GEN:stop --> | :white_check_mark: | :white_check_mark: | :white_check_mark: |

Headless execution is supported for all browsers. Check out system requirements for details.


Installation

Cypress can be installed via npm or yarn.

Using npm
The easiest way to get started with Cypress is to install it as a dev dependency.
```Shell
# Install Cypress
npm install cypress --save-dev
# Open the Cypress App
npx cypress open
```

This will create a cypress folder with example tests and configuration files.
Headless Mode

To run tests in the terminal without opening the GUI (useful for CI/CD or Codespaces).
```Shell
	npx cypress run
```
* [Getting started](https://docs.cypress.io/app/get-started/install-cypress)
* [API reference](https://docs.cypress.io/app/end-to-end-testing/writing-your-first-end-to-end-test)

Capabilities
Time Travel • Debuggability

Time Travel. Cypress takes snapshots as your tests run. Hover over commands in the Command Log to see exactly what happened at each step.

Debuggability. Stop guessing why your tests are failing. Debug directly from familiar tools like Chrome DevTools. Our readable errors and stack traces make debugging lightning fast.
Real-time • Automatic Waiting

Real-time Reloads. Cypress automatically reloads whenever you make changes to your tests. See commands execute in real-time in your app.

Automatic Waiting. Never add waits or sleeps to your tests again. Cypress automatically waits for commands and assertions before moving on. No more async hell.
Spies, Stubs, and Clocks

Network Control. Verify and control the behavior of functions, server responses, or timers. The same functionality you love from unit testing is now right at your fingertips.

Consistent Results. Cypress runs in the same run-loop as your application. This means you have native access to every single object.
Examples

To learn how to run these Cypress examples, check out our [kitchen sink app](https://docs.cypress.io/app/get-started/install-cypress)

Page screenshot
This code snippet navigates to Cypress homepage and saves a screenshot.

```JavaScript

describe('Screenshot Test', () => {
  it('Takes a screenshot of the homepage', () => {
    cy.visit('https://www.cypress.io/');
    cy.screenshot('example-screenshot');
  });
});
```

Mobile Viewport
This snippet sets the viewport to resemble an iPhone X, navigates to a site, and asserts visibility.

```JavaScript

describe('Mobile Viewport', () => {
  it('Render correctly on mobile', () => {
    // Set viewport to iPhone X size
    cy.viewport('iphone-x'); 
    
    cy.visit('https://www.example.com');
    cy.contains('More information').click();
    
    // Check if the URL includes the path
    cy.url().should('include', '/');
  });
});
```

Intercept network requests

This code snippet sets up request routing (Interception) to mock a network response.

```JavaScript

describe('Network Intercept', () => {
  it('Mocks a GET request', () => {
    // Intercept the API call
    cy.intercept('GET', '/api/users', {
      statusCode: 200,
      body: [{ name: 'John Doe' }] // Mock response
    }).as('getUsers');

    cy.visit('/users');
    
    // Wait for the request to finish
    cy.wait('@getUsers');
    cy.contains('John Doe').should('be.visible');
  });
});
```

Custom Commands
This snippet shows how to use a custom command (e.g., defined in commands.js) to simplify login.

```JavaScript
describe('Login Test', () => {
  it('Logs in using custom command', () => {
    // Assuming cy.login() is defined in support/commands.js
    cy.login('username', 'password');
    
    cy.url().should('include', '/dashboard');
    cy.get('.welcome-msg').should('contain', 'Welcome back');
  });
});
```

Resources

* [Documentation](https://docs.cypress.io/app/get-started/why-cypress)
  
* [API reference](https://docs.cypress.io/api/table-of-contents)
  
* [Plugins](https://docs.cypress.io/app/plugins/plugins-list)

* [Changelog](https://docs.cypress.io/app/references/changelog)


