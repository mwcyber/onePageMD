# Open Cyber Index

## Introduction

Simple collection of useful sites and web apps divided by categories.
The main categories collected are Cybersecurity and general IT.

## What is it

The basic project is a frontend that renders a series of md files in which the favorite sites are collected.

The main technologies used are:
- Svelte
- Bootstrap
- Marked library

## How it works

All md files are saved in the '/asset/pages/' folder and the main page loads them dynamically.

The javascript code of the main page provides in a variable a small list in which the points to the files to be shown are collected.

The md files added to the list are rendered automatically.

To create a new page in the list just create the relevant md file and add it to the following list:

```
const files = [
    { value: "cybersecurity.md", label: "Cybersecurity" },
    { value: "network.md", label: "Network" }.
    ...
  ];
```

## Getting Started

If you want to run local the website follow these steps:

1. **Clone the Repository:**

   First, clone this repository to your local machine using Git:

   ```bash
   git clone https://github.com/your-username/mybookmarks.git
   ```

2. **Install Dependencies:**

   Navigate to the project's root directory:

   ```bash
   cd <app-name>
   ```

   Then, install the project dependencies using npm:

   ```bash
   npm install
   ```

3. **Run the Development Server:**

   Start the development server by running the following command:

   ```bash
   npm run dev
   ```

   This command will start a local development server, usually on http://localhost:5173.

## Contributing

If you'd like to contribute to openIndex web app component, please follow these guidelines:

1. Fork the repository and create a new branch.
2. Make your changes and ensure that the code passes linting and testing.
3. Submit a pull request.

If you want to edit the contents of the lists to add or remove a resource:
1. Edit the corresponding md file respecting the format
2. Submit a pull request

## License
Project cyberNewsBot

Copyright © 2023 mwcyber

This project is licensed under the Creative Commons
Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0).

You can find a copy of the license in this directory or visit [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) for more information.