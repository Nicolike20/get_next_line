# get_next_line

## 📚 About the Project

**get_next_line** is a project from the 42 coding school curriculum that involves implementing a function capable of reading a file line by line from a given file descriptor. The goal is to return each line of a text input every time the function is called, handling memory allocation and buffering internally.

This project strengthens understanding of low-level file I/O in C, dynamic memory allocation, buffer management, and handling edge cases such as incomplete lines, end-of-file, or multiple file descriptors simultaneously.

---

## 🧩 Project Objective

Implement the following function:

```c
char *get_next_line(int fd);
```

This function:
- Returns a line from the file descriptor `fd` each time it is called
- Manages internal buffer state between calls
- Handles multiple file descriptors simultaneously (Bonus)
- Returns `NULL` when there are no more lines to read or in case of error

---

## 🔧 Features

- Supports configurable buffer size via `BUFFER_SIZE` macro
- Handles:
  - Lines of arbitrary length
  - Partial reads between buffer boundaries
  - Memory leaks and invalid accesses
- Bonus version includes:
  - Support for reading from multiple file descriptors simultaneously
  - Clean modular code and separation of concerns

---

## 🛠️ How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/get_next_line.git
   cd get_next_line
   ```

2. Compile with your own files, linking `get_next_line.c` and its helper functions:
   ```bash
   gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c main.c
   ```

3. Example usage in your code:
   ```c
   #include "get_next_line.h"

   int fd = open("file.txt", O_RDONLY);
   char *line;
   while ((line = get_next_line(fd)))
   {
       printf("%s", line);
       free(line);
   }
   close(fd);
   ```

---

## 🧠 Skills Demonstrated

- Low-level file I/O with `read()`
- Manual memory allocation and deallocation
- Buffer management and string manipulation
- Managing multiple file descriptors (Bonus)
- Defensive programming and error handling
- Clean modular C code and header files

---

## 📁 Project Status

✅ Completed – fully functional, tested, and compliant with project specifications. 

---

## 📌 Notes

- The implementation is subject to the strict constraints of the 42 school's C coding standards.
- No use of standard library functions other than `read`, `malloc`, and `free` (and `open`, `close` for testing).
- Includes both mandatory and bonus versions (if applicable).

---

## 📫 Contact

Feel free to reach out via [GitHub](https://github.com/yourusername) if you have any questions or want to connect.

[![forthebadge](https://forthebadge.com/images/featured/featured-built-with-love.svg)](https://forthebadge.com)
