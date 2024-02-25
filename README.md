# JSON Forms React seed App

This seed demonstrates how to use [JSON Forms](https://jsonforms.io) with React in order to render a simple form for displaying a task entity.

It is based on `create-react-app` and only contains minor modifications.

- Execute `npm ci` to install the prerequisites. If you want to have the latest released versions use `npm install`.
- Execute `npm start` to start the application.

Browse to http://localhost:3000 to see the application in action. 

 ## Overview

JSON Forms is a powerful library for building dynamic forms in React applications. This seed project provides a starting point for integrating JSON Forms into your React projects.The project shows how JSON Forms and React can be combined to quickly create dynamic forms that improve user experience, allow for flexible data handling, encourage customisation, and simplify form creation. Its modular architecture also demonstrates maintenance and scalability. JSON Forms is an open-source project for community collaboration and an educational resource because it can be used in a variety of domains.

## Prerequisites and Knowledge Required:

Before diving into the project code, users should have a basic understanding of the following:

- **React:** Familiarity with React and its concepts such as components, props, and state is essential as this project is built using React.

- **JavaScript/TypeScript:** Proficiency in JavaScript/TypeScript is necessary as the project code is written primarily in these languages.

- **JSON Schema:** Understanding of JSON schema and its usage in defining the structure of data entities is helpful for working with the project's schema.json file.

- **UI Design:** Some knowledge of UI design principles and best practices can aid in understanding the UI schema (uischema.json) and custom components' layout and functionality.

- **JSON Forms:** Although not required, familiarity with JSON Forms library and its usage in React applications can facilitate understanding and customization of the form rendering process.


## Usage Guide

The repository offers a versatile solution for integrating JSON Forms into your React projects. Below are instructions on how to utilize the repository effectively, along with examples of common usage scenarios.

To start using JSON Forms in your React project, follow these steps:

1. **Install Dependencies**: Ensure you have Node.js and npm installed. Then, navigate to your project directory and run:

    ```bash
    npm install @jsonforms/react @jsonforms/material-renderers
    ```

2. **Import Components**: In your React component file where you want to use JSON Forms, import the necessary components:

    ```jsx
    import { JsonForms } from '@jsonforms/react';
    import { materialRenderers, materialCells } from '@jsonforms/material-renderers';
    ```

### Basic Usage

Once you've installed the dependencies and imported the components, you can use JSON Forms in your React component as follows:

```jsx
import React, { useState } from 'react';
import { JsonForms } from '@jsonforms/react';
import { materialRenderers, materialCells } from '@jsonforms/material-renderers';

const MyFormComponent = () => {
  const [formData, setFormData] = useState({});

  const handleChange = ({ data }) => {
    setFormData(data);
  };

  return (
    <div>
      <h2>My JSON Form</h2>
      <JsonForms
        schema={mySchema}
        uischema={myUISchema}
        data={formData}
        renderers={materialRenderers}
        cells={materialCells}
        onChange={handleChange}
      />
    </div>
  );
};

export default MyFormComponent;
```

## Scenario: Task Management with Our Web Application

Imagine Sarah, a project manager in our marketing company, requires a reliable tool to manage tasks more effectively across several projects. This is how she makes use of our online application:

Sarah enters the website which is designed to help her manage her tasks effectively. The form that addresses her is simple and easy to use, designed to capture important information specific to each task:

- **Task Name:** Sarah can input a descriptive name for the task, such as "Design New Website Landing Page".
- **Description:** A text area allows Sarah to provide comprehensive details, ensuring clear communication and understanding of task requirements.
- **Due Date:** Sarah selects the deadline for task completion, ensuring timely delivery.
- **Completion Status:** With a simple checkbox, Sarah indicates whether the task is completed or not, aiding in tracking progress.
- **Rating:** Sarah assigns a priority rating to the task, guiding her team's focus on critical tasks.
- **Recurrence:** If the task recurs, Sarah can choose from options like "Daily," "Weekly," or "Monthly," enhancing efficiency in managing recurring tasks.
- **Recurrence Interval:** Sarah specifies the interval between task recurrences, ensuring timely execution.

Sarah meticulously fills out the form, providing all necessary details for effective task management. She submits the form, receiving prompt confirmation of successful task creation.

#### How Our Project Helps:

Our web application empowers Sarah and her team with the following benefits:

1. **Streamlined Task Management:** Our intuitive form simplifies the task creation process, allowing Sarah to input and manage task details effortlessly.

2. **Clear Communication:** The descriptive fields in our form facilitate clear communication of task requirements, minimizing misunderstandings and ensuring tasks are completed accurately.

3. **Timely Execution:** By specifying due dates and recurrence options, Sarah ensures tasks are completed on time, enhancing overall project efficiency.

4. **Prioritization:** The priority rating feature enables Sarah to prioritize tasks effectively, guiding her team's focus on critical activities and deadlines.

5. **Enhanced Productivity:** With our web application, Sarah and her team can manage tasks efficiently, freeing up time for other essential project activities and increasing overall productivity.

Our project serves as a valuable tool for Sarah and her team, enabling seamless task management and fostering collaboration and productivity in their projects.

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

## Dependencies

The project relies on several key dependencies to enable its functionality. Below is a list of the main dependencies along with their purpose within the project:

### 1. React

- **Description**: React is a JavaScript library for building user interfaces. It provides a declarative and efficient way to create UI components.
- **Purpose in Project**: The project utilizes React for its frontend development, allowing for the creation of dynamic and interactive user interfaces.

### 2. Material-UI (MUI)

- **Description**: Material-UI is a popular React UI framework that implements Google's Material Design principles. It provides pre-designed React components for building stylish and responsive web applications.
- **Purpose in Project**: Material-UI is used to style and structure the components of the project's user interface, ensuring a consistent and visually appealing design.

### 3. JSONForms

- **Description**: JSONForms is a library for dynamically rendering forms based on JSON schemas and UI schemas. It simplifies the process of creating complex forms by abstracting away the UI rendering logic.
- **Purpose in Project**: JSONForms is a crucial dependency for rendering the project's forms dynamically based on the provided JSON schemas, reducing development time and complexity.

### 4. Cypress

- **Description**: Cypress is an end-to-end testing framework for web applications. It enables developers to write automated tests that simulate user interactions within the browser environment.
- **Purpose in Project**: Cypress is used to automate the testing of the project's frontend functionality, ensuring that the application behaves as expected across different scenarios and environments.

### 5. Other Dependencies

- **@mui/material**: Material-UI core components and styles.
- **@jsonforms/core**: Core functionality for JSONForms.
- **@jsonforms/react**: React bindings for JSONForms.
- **@jsonforms/material-renderers**: Material-UI renderers for JSONForms.
- **@mui/styles**: Styles API for customizing Material-UI components.



## Rendering JSON Forms

JSON Forms is rendered by importing and using the `JsonForms` component and directly handing over the `schema`, `uischema`, `data`, `renderer` and `cell` props. We listen to changes in the form via the `onChange` callback.

#### Using JSON Forms

JSON Forms is rendered by importing and using the `JsonForms` component and directly handing over the `schema`, `uischema`, `data`, `renderer`, and `cell` props. Changes in the form are listened to via the `onChange` callback.

#### Example:

```jsx
import React, { useState } from 'react';
import { JsonForms } from '@jsonforms/react';
import { materialRenderers, materialCells } from '@jsonforms/material-renderers';
import { mySchema, myUISchema } from './formSchema'; // Import your JSON schema and UI schema

const MyFormComponent = () => {
  const [formData, setFormData] = useState({}); // State to hold form data

  const handleChange = ({ data }) => {
    setFormData(data); // Update form data on change
  };

  return (
    <div>
      <h2>My JSON Form</h2>
      <JsonForms
        schema={mySchema}
        uischema={myUISchema}
        data={formData}
        renderers={materialRenderers}
        cells={materialCells}
        onChange={handleChange}
      />
    </div>
  );
};

export default MyFormComponent;
```

# Custom renderers

Custom renderers allow you to define custom components for rendering form controls in JSON-forms React projects. This feature enables you to create specialized or visually customized form elements tailored to your specific needs.

#### Overview:

- **What are Custom Renderers?**: Custom renderers are React components that replace the default rendering behavior of form controls provided by JSON-forms.
- **Why Use Custom Renderers?**: Custom renderers provide flexibility and customization options beyond the default form controls, allowing you to create unique user interfaces and interactions.

#### Implementation:

To implement a custom renderer in your JSON-forms React project, follow these steps:

1. **Create the Custom Renderer Component**: Define a React component that represents the custom form control.

2. **Register the Custom Renderer**: Register the custom renderer component with the JSON-forms library, specifying the mapping between JSON schema types and the custom renderer component.

3. **Use the Custom Renderer**: In your JSON schema, specify the custom renderer component to use for rendering specific form controls by setting the `$ref` property to the custom renderer component's identifier.


 
# Configuration Options:

- **Validation Rules:** Define custom validation rules for form fields to ensure data integrity and accuracy.
  - Example: `<JSONField name="name" label="Name" validationRules={{ required: true }} />`

- **Styling Options:** Customize the appearance of form elements by applying inline styles or CSS classes.
  - Example: `<JSONForm style={{ backgroundColor: '#f0f0f0', padding: '20px' }}>`

- **Layout Configuration:** Organize form fields in different arrangements or layouts to enhance user experience.
  - Example: `<JSONForm style={{ display: 'flex', flexDirection: 'column' }}>`

- **Advanced Options:** Explore advanced options for integrating with external libraries or APIs to extend functionality.
  - Example: Integration with Yup validation library:
    ```jsx
    import * as Yup from 'yup';

    const validationSchema = Yup.object().shape({
      name: Yup.string().required('Name is required'),
      email: Yup.string().email('Invalid email').required('Email is required'),
    });

    <JSONForm validationSchema={validationSchema}>
      {/* Form fields */}
    </JSONForm>
    ```

# Code Synopsis

## `schema.json`

- Defines how data should be organized and checked.
- Includes details like task name, description, due date, completion status, rating, recurrence, and how often it repeats.

## `uischema.json`

- Plans out how the form looks and works.
- Sets up where each piece of information should go and how it's shown.

## React Components:

### `App.js`

- Starts the app and shows the form.
- Lets you add and change tasks easily.

### `Rating.js`

- Shows stars you can click on to rate tasks.
- Makes it simple to give tasks a score.

### `RatingControl.js`

- Helps connect the rating stars to the form.
- Ensures the rating is saved when you fill out the form.

### `index.js`

- Sets up the app to look nice with colors and shapes.
- Makes sure everything runs smoothly when you use the form.


# Testing

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


# Troubleshooting:

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

# some other key features

- Simplifying Form Creation: Rapid Prototyping
- Enhancing User Experience: User-Friendly Forms
- Flexible Data Handling
- Customization and Extensibility: Custom Components
- Scalability and Maintenance: Modular Architecture
- Applicability to Various Domains: Cross-Domain Applications
- Learning Resource: Educational Resource
- Open-Source Contribution: Community Collaboration

# Project Summary
Our project offers a useful and adaptable way to use JSON Forms to create dynamic forms in React applications. Through the simplification of form creation, improvement of user experience, flexible data handling, and encouragement of customisation and extensibility, our project enables developers to create top-notch applications in a range of subjects. It also promotes cooperation among developers by acting as an essential educational tool and encouraging open-source contribution.

# Contributors

Thank you to the following contributors who have participated in this project:

- [Edgar Müller](https://github.com/edgarmueller)

- [Florian Gareis](https://github.com/TheZoker)

- [Stefan Dirix](https://github.com/sdirix)

- [Alexandra Buzila](https://github.com/AlexandraBuzila)

- [Lukas Boll](https://github.com/LukasBoll)

- [Abraham Williams](https://github.com/abraham)

- [Maximilian Koegel](https://github.com/koegel)

- [Eugen Neufeld](https://github.com/eneufeld)


### Edgar Mueller

- **Number of Commits:** 35


### TheZoker

- **Number of Commits:** 12


### sdirix

- **Number of Commits:** 6


### Alexandra Buzila

- **Number of Commits:** 6


### Lukas Boll

- **Number of Commits:** 4


### Abraham

- **Number of Commits:** 1


### Koegel

- **Number of Commits:** 1


### Eneufeld

- **Number of Commits:** 1




