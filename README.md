# Online Compiler
A simple online compiler to run code written in C++, Java, and Python. The application allows users to write code, run it on the server, view the output, and even import/export their code from/to a file.

## Features
- **Code Editor**: Built using CodeMirror for a rich, interactive code editing experience.
- **Language Support**: Supports C++, Java, and Python programming languages.
- **Code Execution**: Sends code to the server to be compiled and run, with the ability to pass input to the program and view output.
- **Import/Export Code**: Allows users to import code from a file and export their code to a `.txt` file.
- **Responsive UI**: The user interface is designed with Bootstrap for a clean and responsive layout.

## Requirements

### Backend (Node.js)
- **Node.js**: Ensure that Node.js is installed on your machine.

  [Download Node.js](https://nodejs.org/)

#### Dependencies:
- **express**: Web framework for Node.js.
- **body-parser**: Middleware to parse JSON request bodies.
- **compilex**: A library for compiling code in multiple languages on the server-side.

Install dependencies by running the following command:

```bash
npm install express body-parser compilex
```

### Frontend
- **CodeMirror**: A versatile text editor to edit the code.
- **Bootstrap**: A CSS framework for creating a responsive design.

## How to Run

### Backend Setup:
1. Clone or download the repository to your machine.
2. Navigate to the project directory and install dependencies:

    ```bash
    npm install
    ```

3. Run the backend server:

    ```bash
    node server.js
    ```

This will start the server on [http://localhost:8000](http://localhost:8000).

### Frontend Setup:
- The `HTML` file (`index.html`) is located in the project directory. Open it in your browser.
- The frontend will make requests to the backend server to compile and execute the code.

## Starting the Application:
1. Open the `index.html` file in a web browser.
2. The CodeMirror editor will be displayed, allowing you to choose the programming language (Java, C++, Python).
3. Write your code in the editor, provide any input if required, and click "Run" to compile and execute your code.
4. The output will be shown in the output textarea.

## Functionality

### Language Selection:
- **Select Language**: Use the dropdown menu to select the programming language (Java, C++, or Python).
- The editor's syntax highlighting will change accordingly.

### Import Code:
- **Import Code**: Click the "Import" button to upload a code file. The content of the file will be loaded into the editor.

### Export Code:
- **Export Code**: Click the "Export" button to download your code as a `.txt` file.

### Run Code:
- **Run Code**: Click the "Run" button to send the code and input (if any) to the server for execution. The output will be displayed in the output section.

## Code Execution (Backend):
- When you click the "Run" button, a `POST` request is sent to the backend (`http://localhost:8000/compile`) with the code and input data.
- The backend processes the request based on the selected language (C++, Java, or Python), compiles the code, and returns the output.
- If the code is valid, the output is displayed in the "Output" section. If there's an error, an error message is shown.

## File Handling:
- **Import Code**: Users can import their code from a file, which is read by JavaScript and loaded into the CodeMirror editor.
- **Export Code**: Users can export their code by downloading it as a `.txt` file.

## Code Explanation

### `server.js` (Backend)
- The backend is built using Express.js, a Node.js framework.
- It uses the `compilex` library to compile the code in different languages (C++, Java, and Python).
- The server listens for incoming requests on port `8000` and processes code execution based on the programming language chosen by the user.
- The server also serves static files for the frontend (HTML, CSS, JS).

### `index.html` (Frontend)
- **CodeMirror** is used for the interactive code editor. It supports syntax highlighting and auto-closing brackets.
- **JavaScript** handles:
  - Switching between programming languages.
  - Sending code to the server and displaying the output.
  - Importing and exporting code via file handling.
- **Bootstrap** is used for the UI layout, making it responsive and user-friendly.

## Running in Production
To deploy this application in a production environment:
- Use a production-ready web server (e.g., Nginx) to serve static files.
- Consider using a cloud service (e.g., Heroku, AWS, etc.) to host the backend.
- Set up environment variables for any sensitive data or configuration.

## License
This project is open-source and available under the MIT License.
