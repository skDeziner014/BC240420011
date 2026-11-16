# CS604 Assignment 1 - Task Manager

Operating Systems (CS604)
Assignment # 01, Fall 2026
Name: Sana Khalid
Student ID: BC240420011

## Program

`task_manager_BC240420011.c` simulates a mini task-processing system using a parent process, a child process, two pipes, and a text report.

- Parent takes the Student ID and three positive integer task execution times.
- Parent creates a child using `fork()` and sends all three times through the first pipe.
- Child calculates the total time and finds the longest task. If times are tied, the task with the smaller task number is selected.
- Child sends the total time, longest task number, and maximum time back through the second pipe.
- Parent displays the results and saves the same report in `<StudentID>_report.txt` using Linux file operations.

Uses `fork()`, `pipe()`, `read()`, `write()`, `close()`, `waitpid()`, `open()`, and file-writing operations.

## Compile and Run (Ubuntu)

```bash
gcc task_manager_BC240420011.c -o task_manager
./task_manager
cat BC240420011_report.txt
```

## Sample Output

```
Enter Student ID: BC240420011
Enter Task 1 Execution Time: 5
Enter Task 2 Execution Time: 8
Enter Task 3 Execution Time: 3

--- Task Processing Report ---
Student ID: BC240420011
Task 1: 5 units
Task 2: 8 units
Task 3: 3 units
Total Execution Time: 16 units
Longest Task: Task 2
Maximum Execution Time: 8 units
Report saved to: BC240420011_report.txt
```

## Files

- `task_manager_BC240420011.c` - C source code
- `BC240420011_report.txt` - Generated report from the sample run above
