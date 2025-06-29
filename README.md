# 🗜️ RLE Compression Program

This repository contains a simple yet effective **Run-Length Encoding (RLE) Compression Program**, developed as part of an internship project for **Algonive**.

---

## 📋 Project Overview

The RLE Compression Program is designed to demonstrate the fundamental principles of data compression using the Run-Length Encoding algorithm. It provides a straightforward way to compress and decompress files by reducing the size of data with repeating patterns. This tool is ideal for educational purposes, learning about compression, or integrating basic RLE compression into other applications.

---

## ✨ Key Features

- **File Compression:** Compress plain text files using the RLE algorithm.
- **File Decompression:** Restore compressed files back to their original state.
- **User-Friendly Interface:** Simple command-line interface for easy interaction.
- **Cross-Platform:** Compatible with major operating systems (Windows, Linux, macOS).

---

## 🛠️ Technologies Used

- **Programming Languages:** C / C++ (or specify your language)
- **Standard Libraries:** File handling, I/O streams, and string processing
- **Compilers:** GCC, Clang, MSVC (as applicable)

---

## 🧑‍💻 How It Works

### 1. Run-Length Encoding (RLE) Algorithm

The RLE algorithm replaces sequences of the same data value occurring in many consecutive data elements with a single data value and a count.

**Example:**  
Input: `AAAAABBBCCDAA`  
Compressed: `5A3B2C1D2A`

### 2. Program Structure

- **Compression Function:** Reads the input file, compresses repeating characters, and writes the result to an output file.
- **Decompression Function:** Reads the compressed file and reconstructs the original data.
- **Main Menu:** Allows the user to choose between compression, decompression, or exiting the program.

---

## 🚀 Getting Started

### 1. Prerequisites

- A C/C++ compiler installed (such as GCC or MSVC)
- Basic knowledge of the command line

### 2. Building the Program

**On Linux/macOS:**

```sh
g++ -o rle_compression rle_compression.cpp
```

**On Windows (using Command Prompt):**

```sh
g++ -o rle_compression.exe rle_compression.cpp
```

> Replace `rle_compression.cpp` with your actual source file name if different.

### 3. Running the Program

After compiling, run the executable from your terminal or command prompt:

```sh
./rle_compression
```
or (on Windows)
```sh
rle_compression.exe
```

---

## 📂 Usage Guide

The program operates through a simple menu system:

1. **Compress a File**
   - Enter the path of the input (plain text) file.
   - Enter the desired output file name for the compressed data.
   - The program will display a success message after compression.

2. **Decompress a File**
   - Enter the path of the compressed file.
   - Enter the desired output file name for the decompressed data.
   - The original file content will be restored.

3. **Exit**
   - Close the program.

---

## 📜 Example Code Snippets

### Compression Logic

```cpp
void compressFile(const std::string& inputPath, const std::string& outputPath) {
    std::ifstream inFile(inputPath);
    std::ofstream outFile(outputPath);
    char current, prev;
    int count = 1;

    if (inFile.get(prev)) {
        while (inFile.get(current)) {
            if (current == prev) {
                ++count;
            } else {
                outFile << count << prev;
                prev = current;
                count = 1;
            }
        }
        outFile << count << prev;
    }
    inFile.close();
    outFile.close();
}
```

### Decompression Logic

```cpp
void decompressFile(const std::string& inputPath, const std::string& outputPath) {
    std::ifstream inFile(inputPath);
    std::ofstream outFile(outputPath);
    int count;
    char ch;

    while (inFile >> count >> ch) {
        for (int i = 0; i < count; ++i)
            outFile << ch;
    }
    inFile.close();
    outFile.close();
}
```

---

## 🧭 Main Menu Loop

The program typically follows this loop:

```cpp
int main() {
    int choice;
    do {
        std::cout << "\n=== RLE Compression Program ===\n";
        std::cout << "1. Compress a File\n";
        std::cout << "2. Decompress a File\n";
        std::cout << "0. Exit\n";
        std::cout << "Select an option: ";
        std::cin >> choice;
        // Call corresponding function based on choice
    } while (choice != 0);
    return 0;
}
```

---

## 📝 Notes

- Only plain text files are supported in this basic version.
- Compression efficiency depends on the repetitiveness of data.
- Error handling is included for invalid file paths or formats.

---

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request with improvements or bug fixes.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Developed as part of an internship project for **Algonive**
- Inspired by classic data compression algorithms and educational resources
