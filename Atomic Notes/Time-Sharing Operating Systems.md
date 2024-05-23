Tags: [[Operating Systems]]
# Time-Sharing Operating Systems

> [!summary] 
> Enables execution of many different tasks and operates in a timed manner where each task is queued for the CPU. 

Also called as a **Multitasking System**

Each task is allocated a unit of time called a *quantum*. The CPU will work on each task for a quantum before rotating to the next task.

This approach is beneficial for task loads with several smaller tasks. It minimizes CPU wait time and every user is given a fair time allocation. This is because the CPU "rotates" on executing the tasks.

The downside to this is that rapid switching between tasks can result in some communication issues with data being mixed up.

![[time-sharing-os.excalidraw|100%|center]]

---
# References

1. Microsoft Cybersecurity Analyst Professional Certificate

___
## Flashcards

Flashcard Tags: #os 

A type of OS where it enables execution of many different tasks and operates in a timed manner where each task is queued for the CPU.
?
Time-Sharing Operating System
