
### OS Mini-Project
Title : Operating System Project  - Synchronization

Author : Mitesh Goplani

Project # : #1 The Sleeping Teaching Assistant

Description : Manage the students (threads) and helping task


### Compile and Run 
1. make/compile
2. ./simulator

### Structure
1. student: student threads have own semaphore
2. ta: ta thread has its own semaphore (ta : Teaching Assistant) 

### Functions
1. stu_programming: Students are waiting in random time (they are programming in this time), and notify to ta for help. If ta is helping a student already, other students are waiting at chairs in hallway, but if chairs are full, students go to their programming task back
2. ta_teaching: ta is sleeping until notification is arrived from at least one student. if any student wakes the ta up, ta will help the student. If helping the student is finished and chairs are empty, then ta go to sleeping back
3. rand_sleep: Make sleeping time (it means programming task or helping tesk) randomly

### Simple process flows
1. make student threads and ta thread (initialize)
2. each thread is running its own thread function (student is programming, ta is sleeping)
3. Student will wake the ta up after random time intervals, then ta will help the arrived student (change student's semaphore to 1 and wait ta's semaphore). But if chairs are full, students go to their programming back and return again after random time interval.
4. If ta's help is finished, ta check the remaining students. If there is(are) student(s) ta is keeping the current state (help continuously) and if not, ta goes back to sleep (change ta's semaphore to 1 and wait student's semaphore)
5. repeat 3-4 steps
