# Metadata-Driven UI with Vue 3

This is a Vue 3 demo application that demonstrates how to build a dynamic, metadata-driven user interface. The UI is generated based on external metadata, allowing the display of components like buttons, counters, and images, where the structure and content of the UI are controlled by the provided metadata.

## Features
- **Dynamic Component Rendering**: Based on metadata, the app dynamically renders components such as `Button`, `Counter`, and `Image`.
- **Style Management**: The `Image` component can accept dynamic styles like width, height, and border properties from metadata.
- **Button Actions**: The `Button` component triggers actions like incrementing a counter or showing an alert when clicked.
- **State Management**: The application shares data between components dynamically using Vue's `props` and event handling.


## Components

### `Button.vue`
A simple button component that accepts an `action` prop. When clicked, it triggers different actions based on metadata:
- **Increment**: Increments a counter.
- **Alert**: Displays a custom alert message.

### `Counter.vue`
Displays a count and provides a method to increment the count. The count is passed through metadata and updated when the button is clicked.

### `Image.vue`
An image component that displays an image using the `src` and `alt` properties from metadata. It also accepts a `style` prop to allow styling through metadata, such as setting width, height, border, and other CSS properties.

### `MetadataProcessor.vue`
This component processes the metadata and dynamically renders the appropriate components. It handles:
- Rendering different types of components like `Button`, `Counter`, and `Image`.
- Passing data and handling events (like button clicks) to control the UI's behavior.

## How to Run

### Prerequisites
- Node.js (v14 or later)
- Vue CLI (or Vite for project setup)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/metadata-driven-ui-vue3.git
   cd metadata-driven-ui-vue3
   npm install
   npm run dev
   This will start a local development server, and you can view the app in your browser at http://localhost:3000.


