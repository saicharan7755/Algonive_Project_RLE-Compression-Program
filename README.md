# RLE Compression & Decompression Tool

A robust and user-friendly file compression and decompression program written in C++ using the Run-Length Encoding (RLE) algorithm. This tool is designed to efficiently reduce file sizes for text-based files and restore their original content with ease.

---

## ✨ Features

- **Intuitive Command-Line Interface**  
  Simple and clear CLI for seamless user experience.

- **Support for Multiple File Types**  
  Works with a variety of text-based file formats (e.g., `.txt`, `.csv`, `.log`).

- **Detailed Compression Statistics**  
  Automatically reports original size, compressed size, and compression ratio after each operation.

- **Robust Error Handling**  
  Gracefully manages invalid inputs, unsupported formats, and corrupted files.

- **Custom Compressed File Format**  
  Uses a distinct file extension for compressed files, ensuring compatibility with the decompression utility.

---

## 🚀 Getting Started

### Prerequisites

- C++ compiler (e.g., `g++`, `clang++`)
- CMake (optional, for build automation)

### Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/saicharan7755/Algonive_Project_RLE-Compression-Program.git
    cd Algonive_Project_RLE-Compression-Program
    ```

2. **Compile the source code:**
    ```bash
    g++ -o rle_compress rle_compress.cpp
    g++ -o rle_decompress rle_decompress.cpp
    ```
    _Or use CMake if provided._

---

## ⚡ Usage

### Compress a File

```bash
./rle_compress <input_file>
```

- Example:
    ```bash
    ./rle_compress sample.txt
    ```
    _Output: `sample.rle`_

### Decompress a File

```bash
./rle_decompress <compressed_file>
```

- Example:
    ```bash
    ./rle_decompress sample.rle
    ```
    _Output: `sample_decompressed.txt`_

---

## 📊 Example

Suppose `input.txt` contains:
```
aaaaabbccccdd
```

After compression:
```
5a2b4c2d
```

Decompression restores the original text.

---

## 🛠️ Project Structure

- `rle_compress.cpp` &mdash; Source code for compression utility
- `rle_decompress.cpp` &mdash; Source code for decompression utility
- `README.md` &mdash; Project documentation

---

## 📎 License

This project is licensed under the [MIT License](LICENSE).

---

## 👤 Author

Developed by [saicharan7755](https://github.com/saicharan7755)

---
