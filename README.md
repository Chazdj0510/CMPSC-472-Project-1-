# File Processing System with Multiprocessing and Multithreading

## Project Overview

This project develops a system to process multiple large files in parallel using **multiprocessing** and **multithreading**, while employing **inter-process communication (IPC)** mechanisms for message passing between processes. The system aims to count the frequency of a specific word (or set of words) in each file and compare the advantages and disadvantages of multiprocessing versus multithreading in terms of performance, resource consumption, and complexity.

## Problem Description

The system accepts a directory containing multiple large text files. Each file is processed in a separate process using `fork()`. Inside each process, multiple threads are created to read and process portions of the file in parallel. The files are sourced from the **Calgary Corpus** and are processed to count word frequencies.

### Files for Processing:

- **bib** (Bibliography) – 111,261 bytes
- **paper1** (Technical paper) – 53,161 bytes
- **paper2** (Technical paper) – 82,199 bytes
- **progc** (C source code) – 39,611 bytes
- **progl** (LISP source code) – 71,646 bytes
- **progp** (PASCAL source code) – 49,379 bytes
- **trans** (Terminal transcript) – 93,695 bytes

You can download the files from [The Calgary Corpus](https://corpus.canterbury.ac.nz/descriptions/#calgary).

## Key Features

1. **Process Creation:**
   - Each child process is responsible for one file.
   - Processes are created using `fork()`.

2. **Multithreading:**
   - Within each process, threads split the file into parts and process each part in parallel to count word frequencies.
   - Compare the performance of single-threaded vs. multi-threaded approaches within the same process.

3. **Inter-Process Communication (IPC):**
   - Use IPC mechanisms (pipes, message queues, or shared memory) for communication between parent and child processes.
   - Child processes communicate word count results back to the parent process.

4. **Performance Comparison:**
   - Measure and compare the performance (time taken, CPU usage, memory usage) of multiprocessing versus multithreading.
   - Discuss trade-offs such as context switching, memory overhead, and parallelism.

## Project Requirements

- **Process Management:** Use `fork()` for process creation and implement synchronization and communication between processes.
- **IPC Mechanism:** Implement message passing between parent and child processes using pipes, message queues, or shared memory.
- **Multithreading:** Use multithreading to enhance file processing speed by processing file chunks in parallel.
- **Error Handling:** Proper error handling for process creation, IPC setup, and multithreading.
- **Performance Evaluation:** Measure and compare the results between multiprocessing and multithreading.

## Deliverables

- **Code:** 
  - The system should be well-structured and modular, with appropriate use of processes, threads, and IPC.
  - Include clear documentation and comments explaining how the system works.
  
- **Report:** 
  - Include a description of the project and an overview of how multiprocessing and multithreading were used.
  - Compare the advantages and disadvantages of each approach.
  - Provide diagrams showing how processes and threads were created, and how communication occurred via IPC.
  - Include performance metrics, word frequency results, and a discussion of findings.

## Instructions

1. **Running the System:**
   - Clone the repository to your local machine.
   - Download the necessary files from [The Calgary Corpus](https://corpus.canterbury.ac.nz/descriptions/#calgary).
   - Compile the C program using `gcc`:
     ```bash
     gcc -o file_processing_system file_processing_system.c -lpthread
     ```
   - Run the compiled program with the following command:
     ```bash
     ./file_processing_system /path/to/files/ directory word_to_count
     ```

2. **Testing:**
   - Use different words to count across multiple files and observe the differences in performance between multiprocessing and multithreading.

## Performance Evaluation

- Include screenshots or examples of file processing.
- Present sample scenarios for word counting, showing the difference in performance between multiprocessing and multithreading.

## Discussion

- Challenges faced during implementation.
- Observed pros and cons of multiprocessing and multithreading.
- Any limitations or suggested improvements.

