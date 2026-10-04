# 🗂️ Local SSD File Mapper

A lightweight, high-performance, single-page web utility that maps and interacts with your local drive partitions and directories right from the browser. Built purely with modern JavaScript using the **File System Access API**, it runs entirely on the client side with zero backend dependencies, database storage, or server tracking.

## 🚀 Features

* **Native Directory Picking:** Seamlessly select folders and drive partitions using the native browser directory picker.
* **Dynamic Grid Layout:** Renders directories with intuitive visual indicators (📁 for folders, 📄 for files).
* **Deep Directory Traversal:** Click into subfolders to dynamically update the scope and navigate deeper into your storage hierarchy.
* **Virtual Binary Downloads:** Tap any file to instantly extract its binary data and trigger a standard browser download without taking up long-term memory overhead.
* **Dark Mode Out-of-the-Box:** Sleek, high-contrast dark theme optimized for long development and mapping sessions.

## 🛠️ Performance & Memory Management

Unlike legacy file utilities that slow down the browser under heavy loads, this tool ensures minimal memory footprints through:
1. **Asynchronous Iteration:** Uses `for await...of` loops to parse folders incrementally instead of blocking the main browser execution thread.
2. **Object URL Lifecycle Cleanup:** Invokes `URL.revokeObjectURL()` immediately after a file download executes to instantly release allocated RAM chunks.

## 📂 Project Structure

```text
├── index.html     # Single monolithic file containing all structure, styles, and logic.
└── README.md      # Project documentation.
```

## ⚡ Quick Start

Since this application utilizes advanced browser security APIs, it requires a secure origin (HTTPS or `localhost`) to run fully.

1. Clone or download this repository.
2. Open the directory in your terminal and spin up a local development server (e.g., using Python, Node.js, or Live Server):
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (via serve)
   npx serve .
   ```
3. Open your browser and navigate to `http://localhost:8000`.
4. Click **Select Directory** to start mapping your local SSD partitions.

## ⚠️ Browser Compatibility

This project relies on the **File System Access API** (`window.showDirectoryPicker`). 

* **Supported Browsers:** Google Chrome, Microsoft Edge, Opera, and other Chromium-based browsers.
* **Unsupported Browsers:** Apple Safari and Mozilla Firefox (due to current strict vendor security constraints around broad file system enumeration).

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
