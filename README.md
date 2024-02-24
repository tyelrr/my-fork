# JSON Forms React seed App

This seed demonstrates how to use [JSON Forms](https://jsonforms.io) with React in order to render a simple form for displaying a task entity.

It is based on `create-react-app` and only contains minor modifications.

- Execute `npm ci` to install the prerequisites. If you want to have the latest released versions use `npm install`.
- Execute `npm start` to start the application.

Browse to http://localhost:3000 to see the application in action.

 ## Overview

JSON Forms is a powerful library for building dynamic forms in React applications. This seed project provides a starting point for integrating JSON Forms into your React projects.

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

 ## Overview

JSON Forms is a powerful library for building dynamic forms in React applications. This seed project provides a starting point for integrating JSON Forms into your React projects.

## Rendering JSON Forms

JSON Forms is rendered by importing and using the `JsonForms` component and directly handing over the `schema`, `uischema`, `data`, `renderer` and `cell` props. We listen to changes in the form via the `onChange` callback.

## Custom renderers

Please see [our corresponding tutorial](https://jsonforms.io/docs/tutorial) on how to add custom renderers.
