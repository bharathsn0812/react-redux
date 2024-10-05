# React Redux Toolkit Counter

This project is a simple counter application built with React and Redux Toolkit. It demonstrates the basic usage of Redux Toolkit for state management in a React application.

## Features

- Increment counter
- Decrement counter
- Increment counter by a specific amount (5 in this example)

## Technologies Used

- React JS
- Redux Toolkit
- React Redux

## Running the Application

To start the development server, run:

```
npm install
npm run start
```

The application will open in your default web browser at `http://localhost:3000`.

## Project Structure

- `src/index.js`: The entry point of the application
- `src/App.js`: The main React component
- `src/app/store.js`: Redux store configuration
- `src/features/counter/counterSlice.js`: Counter slice with reducers and actions

## Usage

The main page displays a counter and three buttons:

- Click "Increment" to increase the counter by 1
- Click "Decrement" to decrease the counter by 1
- Click "Increment by 5" to increase the counter by 5
