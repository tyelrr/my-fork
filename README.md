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

Please see [our corresponding tutorial](https://jsonforms.io/docs/tutorial) on how to add custom renderers.
### Links and References:

- [JSON Forms](https://jsonforms.io): Official website of JSON Forms library.
- [React](https://reactjs.org): Official website of React library.
- [Material-UI](https://mui.com): Official website of Material-UI library.
- [JSON Schema](https://json-schema.org): Official website of JSON Schema standard.
- [Tutorial on Adding Custom Renderers](https://jsonforms.io/docs/tutorial-custom-renderers): Link to the corresponding tutorial on JSON Forms website.

- ### Troubleshooting:

#### Form Not Rendering:

**Issue:** The form does not render or appears blank.

**Troubleshooting Tips:**
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

