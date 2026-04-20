# Create a markdown file with the project plan
markdown_content = """# Project 3: Multithreading - Team Work Plan

This document outlines the task distribution and project timeline for a two-member team working on the Operating System Multithreading lab.

## Task Distribution

| Member | Primary Responsibility | Key Deliverables |
| :--- | :--- | :--- |
| **Member A** | **Part 1: Uthread (xv6)** | Implement `thread_create()` and `thread_schedule()` in `user/uthread.c`, and `thread_switch` in `user/uthread_switch.S`. |
| **Member B** | **Part 2 & 3: Pthreads (Linux)** | Implement bucket-level locking in `notxv6/ph.c` and synchronization logic in `notxv6/barrier.c`. |
| **Shared** | **Testing & Documentation** | Debugging with GDB, passing `make grade`, and writing the `Report.pdf`. |

---

## Project Plan

### Phase 1: Environment Setup & Research (Days 1–3)
* **Both Members**: Set up the xv6 environment, clone the repository, and switch to the `thread` branch.
* **Both Members**: Read **Chapter 8: Scheduling** from the xv6 book to understand context switching.
* **Member A**: Study `user/uthread.asm` to understand the RISC-V assembly requirements for saving/restoring registers.
* **Member B**: Research `pthread_mutex` and `pthread_cond_wait` documentation.

### Phase 2: Core Development (Days 4–10)
* **Member A (Uthread Implementation)**:
    * Modify `struct thread` to hold saved registers.
    * Write the assembly for `thread_switch` to handle callee-save registers.
    * Update `thread_schedule()` to call the switch function.
* **Member B (Concurrency Implementation)**:
    * **Hash Table**: Identify the race condition in `put()` and `insert()`. Implement a per-bucket lock to pass both `ph_safe` and `ph_fast` tests.
    * **Barrier**: Implement `barrier()` using condition variables, ensuring `bstate.round` increments correctly and handling race conditions between rounds.

### Phase 3: Integration & Debugging (Days 11–13)
* **Member A**: Use `riscv64-linux-gnu-gdb` to single-step through `thread_switch` and verify stack pointers.
* **Member B**: Stress test the hash table and barrier with varying numbers of threads (1, 2, and more).
* **Both Members**: Run `make grade` to ensure all tests pass simultaneously.

### Phase 4: Final Submission (Day 14)
* **Shared**: Draft the `StudentID1_StudentID2_Report.pdf` explaining the solutions and any challenges faced.
* **Shared**: Generate the git patch file (`git diff > <ID1_ID2>.patch`) and prepare the final `.zip` following the specific naming format.

---

## Submission Checklist
* [ ] **Report**: `StudentID1_StudentID2_Report.pdf` (No source code included).
* [ ] **Patch**: `StudentID1_StudentID2.patch`.
* [ ] **Source**: Zip file of clean xv6.
* [ ] **Archive**: Final file named `StudentID1_StudentID2.zip` (where ID1 < ID2).
"""

