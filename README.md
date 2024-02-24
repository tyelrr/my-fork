# JSON Forms React seed App

This seed demonstrates how to use [JSON Forms](https://jsonforms.io) with React in order to render a simple form for displaying a task entity.

It is based on `create-react-app` and only contains minor modifications.

- Execute `npm ci` to install the prerequisites. If you want to have the latest released versions use `npm install`.
- Execute `npm start` to start the application.

Browse to http://localhost:3000 to see the application in action.

 ## Overview

JSON Forms is a powerful library for building dynamic forms in React applications. This seed project provides a starting point for integrating JSON Forms into your React projects.
The project demonstrates how JSON Forms can be integrated with React to create dynamic forms quickly, simplifying form creation, enhancing user experience, enabling flexible data handling, and promoting customization. It also showcases scalability and maintenance through its modular architecture. JSON Forms can be applied to various domains, making it an educational resource and open-source project for community collaboration.

## File Structure

The project's file structure is organized as follows:

- `src/schema.json`: Contains the JSON schema (data schema) for defining the structure of a task entity.
- `src/uischema.json`: Contains the UI schema for specifying the layout and controls for rendering the task form.
- `src/index.tsx`: The entry point of the application where the Material UI theme customization is applied to give each control more space.
- `src/App.tsx`: The main app component that utilizes the `JsonForms` component to render the form.
- `src/Rating.tsx`: A custom React component for rendering a rating control in the form.
- `src/RatingControl.tsx`: Integrates the custom rating control with JSON Forms.
- `src/RatingControlTester.ts`: Defines a control tester to determine the rank of the rating control.

The [data schema](src/schema.json) defines the structure of a Task: it contains attributes such as title, description, due date and so on.

The [corresponding UI schema](src/uischema.json) specifies controls for each property and puts them into a vertical layout that in turn contains two horizontal layouts.


## Rendering JSON Forms

JSON Forms is rendered by importing and using the `JsonForms` component and directly handing over the `schema`, `uischema`, `data`, `renderer` and `cell` props. We listen to changes in the form via the `onChange` callback.

## Custom renderers

### Custom Renderers:

Custom renderers allow you to define custom components for rendering form controls in JSON-forms React projects. This feature enables you to create specialized or visually customized form elements tailored to your specific needs.

#### Overview:

- **What are Custom Renderers?**: Custom renderers are React components that replace the default rendering behavior of form controls provided by JSON-forms.
- **Why Use Custom Renderers?**: Custom renderers provide flexibility and customization options beyond the default form controls, allowing you to create unique user interfaces and interactions.

#### Implementation:

To implement a custom renderer in your JSON-forms React project, follow these steps:

1. **Create the Custom Renderer Component**: Define a React component that represents the custom form control.

2. **Register the Custom Renderer**: Register the custom renderer component with the JSON-forms library, specifying the mapping between JSON schema types and the custom renderer component.

3. **Use the Custom Renderer**: In your JSON schema, specify the custom renderer component to use for rendering specific form controls by setting the `$ref` property to the custom renderer component's identifier.


## Rendering JSON Forms

JSON Forms is rendered by importing and using the `JsonForms` component and directly handing over the `schema`, `uischema`, `data`, `renderer` and `cell` props. We listen to changes in the form via the `onChange` callback.




## Testing

#### Overview
The testing suite for this project ensures the reliability, functionality, and user experience of the application. It includes integration tests for key features and components, ensuring they behave as expected under various scenarios.

#### Test Suite Structure
The testing suite consists of integration tests written using Cypress, a powerful end-to-end testing framework for web applications.

**Files and Directories:**
- **Integration Tests:** Cypress integration tests are located in the `cypress/integration` directory.
- **Custom Commands:** Custom Cypress commands are defined in the `cypress/support/commands.js` file.
- **Plugin Configuration:** Cypress plugin configuration is set in the `cypress/plugins/index.js` file.
- **Support Files:** Additional support files and utilities for testing are located in the `cypress/support` directory.

#### Running Tests
To execute the tests locally, follow these steps:

1. Ensure that the project dependencies are installed by running `npm install`.
2. Start the development server by running `npm start`.
3. Open a new terminal window and run Cypress with `npx cypress open`.
4. Cypress Test Runner will open. Click on the desired test file to run the tests.

#### Test Coverage
**Form Component:**
The integration tests for the form component validate various aspects of its functionality, including:
- Changing input values and verifying data updates accordingly.
- Displaying error messages for invalid input.
- Ensuring proper behavior of form elements such as checkboxes, dropdowns, and date pickers.

#### Custom Commands
Custom Cypress commands are used to streamline test code and improve readability. Examples of custom commands include:
- `login`: Simulates user login with provided credentials.
- `drag`: Performs a drag action on a specified element.
- `dismiss`: Dismisses an element, if present.

#### Plugin Configuration
The `plugins/index.js` file is used to define custom plugins and configure Cypress behavior. It can be extended to include custom commands or modify Cypress configuration settings.

#### Support Files
Support files in the `support` directory contain utility functions, setup code, and other resources needed for testing. These files contribute to the organization and efficiency of the testing suite.

#### Testing Best Practices
- Write descriptive test cases with clear expectations to ensure test readability.
- Maintain a clean and organized test suite structure for easy maintenance and collaboration.
- Regularly review and update tests to reflect changes in application functionality or requirements.

#### Troubleshooting
If you encounter any issues while running tests, refer to the troubleshooting section in the README.md or consult the Cypress documentation for guidance.


## Troubleshooting:

#### Form Not Rendering:

**Issue:** The form does not render or appears blank.

##Troubleshooting Tips:
- Check if the JSON schema (`schema.json`) and UI schema (`uischema.json`) are properly configured and accessible.
- Ensure that the form data is provided to the `JsonForms` component and is valid according to the schema.

**Solution:** Verify the correctness of the schema, UI schema, and data, and make necessary corrections.



#### Custom Renderer Not Working:

**Issue:** Custom renderers for form controls are not rendering as expected.

**Troubleshooting Tips:**
- Verify that the custom renderer components are properly implemented and registered with the `JsonForms` component.
- Check for any errors or warnings in the console that may indicate issues with the custom renderer implementation.

**Solution:** Review the custom renderer code, ensure it conforms to the expected interface, and debug any issues with rendering logic.


#### Form Data Not Updating:

**Issue:** Form data does not update when user inputs are changed.

**Troubleshooting Tips:**
- Confirm that the `onChange` callback function is properly set up and receiving updated form data.
- Check for any errors in the form data structure or inconsistencies between the schema and UI schema.

**Solution:** Debug the `onChange` event handling logic, ensure that updated form data is correctly propagated, and validate the data against the schema.

