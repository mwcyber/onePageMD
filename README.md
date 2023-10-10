# onePageMD

## Introduction

This project is a frontend application designed to display a series of markdown (md) files on a single page, allowing users to select and view the content of their choice. Whether you're creating documentation, a personal wiki, or any content-driven application, onePageMD simplifies the process of organizing and presenting multiple markdown files.

## What is it?

This project serves as a user-friendly interface for rendering markdown files within a single web page. 

The primary technologies employed in this project include:

- **Svelte:** A modern JavaScript framework for building user interfaces.
- **Bootstrap:** A popular CSS framework for styling and layout.
- **Marked library:** A markdown parser and compiler for JavaScript.

## How it works

All markdown files are stored in the `/asset/pages/` folder, and the main page dynamically loads and renders them. The JavaScript code on the main page manages a small list containing references to the files to be displayed. As files are added to this list, they are automatically rendered on the page.

To add a new page to the list, simply create the corresponding markdown file and append its details to the list in the code snippet below:

```javascript
const files = [
    { value: "page01.md", label: "Page one label" },
    { value: "page02.md", label: "Page two label" },
    // Add more pages as needed
  ];
```

## Getting Started

If you want to run the project locally, follow these steps:

1. **Clone the Repository:**

   Clone this repository to your local machine using Git:

   ```bash
   git clone https://github.com/your-username/project-name.git
   ```

2. **Install Dependencies:**

   Navigate to the project's root directory:

   ```bash
   cd <app-name>
   ```

   Install the project dependencies using npm:

   ```bash
   npm install
   ```

3. **Run the Development Server:**

   Start the development server by running the following command:

   ```bash
   npm run dev
   ```

   This command will launch a local development server, typically on http://localhost:5173.

## Contributing

If you'd like to contribute to the project, please follow to these guidelines:

1. Fork the repository and create a new branch.
2. Make your changes and ensure that the code passes linting and testing.
3. Submit a pull request.

## License

**Project onePageMD**

Copyright © 2023 mwcyber

This project is licensed under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0)](https://creativecommons.org/licenses/by-nc-nd/4.0/). You can find a copy of the license the provided link for more information.
