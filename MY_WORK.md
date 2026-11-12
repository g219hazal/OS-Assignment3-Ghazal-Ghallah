# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Ghazal Ghallah] |
| **Student ID** | [446051422] |
| **University Email** | [446051422@std.psau.edu.sa]|
| **GitHub Username** | [g219hazal] |
| **Repository Link** | [(https://github.com/g219hazal/OS-Assignment3-Ghazal-Ghallah)]|
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 4, 2026, 7:15 PM]
**What I did**:
Forked the starter repo, set my student ID and ran the original code
**Details**:
Forked the starter repository and renamed it to OS-Assignment3-Ghazal-Ghallah
Changed the student ID on line 304 to 446051422 (14 processes, quantum 5000ms, 4 CPUs)
Ran the original starter: all 4 CPUs picked P1 at the same time, 3 CPUs crashed with IllegalThreadStateException, and the watchdog stopped the program
Saved the output in a text file for Question 1. Commit: "Set my student ID"
**Challenges**:
When I saved the file, VS Code formatted the whole file automatically and my student ID moved from line 304 to line 345. Also the first commit failed because
it asked for user.name and user,emai.
**Solution**:
 I discarded the changes and saved with "Save without Formatting" (Ctri+K then S). I set git config with my name and my university email
**Time spent**:
35 minutes
---

### Entry 2 - [November 4, 2026, 7:50 PM]
**What I did**:
Feature 1 - protected the ready queue with a ReentrantLock
**Details**:
Added `import java.util.concurrent.locks.ReentrantLock`
 Added `queueLock` in ReadyQueue
 Put lock() / try / finally { unlock() } in add(), poll(), processOf() and snapshot()
  In poll() I kept the return inside try, the finally still releases the lock
 After running: every CPU picked a different process (P1, P2, P3, P4), no exception, completed processes became 14/14
 Context switches (20/24) and service time (72570/82570) were still wrong, this is for Feature 2
 Commit: "Feature 1: fixed the race on the ready queue using ReentrantLock"
**Challenges**:
In the starter output P2, P3 and P4 never ran (0 in the summary table) and I did not understand why at first
**Solution**:
I read poll() again: two CPUs read the same head, then each one removes a different element, so some processes were removed without running
**Time spent**:
45 minutes
---

### Entry 3 - [November 11, 2026, 10:05 PM]
**What I did**:
Feature 2 - protected the shared statistics
**Details**:
 I chose one lock per counter: contextSwitchLock, completedLock, serviceTimeLock, because the three counters are independent
 Protected the 3 update methods and the 3 getters with lock() / try / finally
 Ran it 3 times: context switches 24/24, completed 14/14, service time 82570/82570 every time
 Busy-waiting polls was still 129 (Feature 3)
 Commit: "Feature 2: added a lock for each counter in SharedStats"
**Challenges**:
When I added the finally block, the line was split in the middle and one closing brace was missing. Also Copilot kept showing suggestions while I was typing
**Solution**:
I used the End key before pressing Enter so the cursor is at the end of the line, fixed the braces, and pressed Esc to ignore the suggestions
**Time spent**:
55 minutes
---

### Entry 4 - [November 11, 2026, 11:00 PM]
**What I did**:
Feature 3 - replaced busy waiting with a counting semaphore
**Details**:
Added `Semaphore readyCount = new Semaphore(0)` in ReadyQueue (0 because the queue starts empty)
release() in add() after the queue lock is released
acquire() in CpuWorker before poll(), outside any lock
Deleted the polling code (Thread.sleep(20) and the if (thread == null) part)
When all processes are completed, the CPU calls release(totalCPUs) to wake up the sleeping CPUs, and a CPU that wakes up checks if everything is completed and stops
Ran it 6 times: all 4 lines ✔, busy-waiting polls = 0, no watchdog
Commit: "Feature 3: replaced busy waiting with a semaphore"
**Challenges**:
While deleting the busy waiting code I deleted the line `Thread thread = readyQueue.poll();` by mistake. A grey Copilot sugestion appeared in its place so I thought it was still there, but `thread` had red errors
**Solution**:
I pressed Esc and typed the line again myself, then the errors disappeared
**Time spent**:
40 minutes
---

### Entry 5 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Incrementing a counter involves three steps (reading, adding, and writing), during which an update could potentially be lost.
I was surprised to see all four processors reach P1 simultaneously.
Any code that modifies shared data requires a lock.
The lock must be released within a `finally` block.
Using a semaphore allowed the processor to sleep instead of constantly checking, which brought the number down from 647 to 0.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The trickiest part was the end of the program in Feature 3.
The processors go to sleep upon calling `acquire`, waiting for a task.
After the final task, no new tasks will arrive, so they would remain asleep forever.
The solution is for the last processor to wake them all up by calling `release(totalCPUs)`.
Once awakened, each processor verifies that everything is complete and then terminates.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I worked on one function at a time, rather than doing everything at once.
After implementing each feature, I ran the program and performed a verification.
I compared the numbers before and after each feature was added.
I ran it multiple times, as synchronization errors don’t always appear on every run.
Whenever I didn’t understand something, I referred back to the code and the README, or asked for an explanation.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Banking: Two transfers from the same account at the same time could cause a balance update to be lost.
Ticket booking: Two people might book the same seat—much like the 'P1' scenario I mentioned.
Inventory in online stores must be protected.
A print queue functions similarly to my queue; the printer waits for tasks rather than constantly checking for them.
Databases use locks for the very same reason.]

### Optional: What would you like to learn more about?

[I want to learn more about deadlocks—how to detect them and how to avoid them in large scale software.]

### Optional: How confident do you feel about synchronization concepts now?

[Intermediate. I understand locks and semaphores, but I need more practice with bounded queues and deadlocks.]

### Optional: Feedback on the assignment

[The assignment was useful because I saw the problem with my own eyes in the output before fixing it. Feature 3 was the most difficult part.]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In my first run, all the values ​​were incorrect: there were 18 context switches instead of 24, and 11 completed tasks instead of 14. This happened because multiple CPUs picked up P1 simultaneously, causing P2, P3, and P4 to be lost. Furthermore, after just one feature was enabled, the service time became 72,570 instead of 82,570—meaning two additions of 5000 ms were lost. A similar issue could occur on a real machine, as the operating system might pause a thread between a read and a write operation; however, since this happens rarely, it is difficult to detect.]

Verification block of the **original starter**: 
```
Context switches (quanta executed)     expected 24       observed 18       ✘ MISMATCH
Completed processes                    expected 14       observed 11       ✘ MISMATCH
Total service time (ms)                expected 82570    observed 57771    ✘ MISMATCH
Busy-waiting polls (must be 0)         expected 0        observed 647      ✘ MISMATCH
WATCHDOG: the simulation did not finish (27 s).
```

Verification block of **my final version**:
```
Context switches (quanta executed)     expected 24       observed 24       ✔
Completed processes                    expected 14       observed 14       ✔
Total service time (ms)                expected 82570    observed 82570    ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
✔ All shared values are consistent.
```
**Explanation of the timeline:**
[CPU-1 reads `totalServiceTime` = 20,000 and pauses. CPU-2 reads the same value, 20,000. CPU-1 writes 25,000, and CPU-2 also writes 25,000. The result is 25,000 instead of 30,000; thus, an addition has been lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used a separate lock for each counter because the three counters are independent, updating the time does not need to wait for a context switch update. The trade off is having more locks and more code. The queue has its own distinct lock because it involves different data, using the same lock would cause the queue to stall unnecessarily while the counters are being updated. The `lock()` method ensures mutual exclusion meaning only one thread can be in the critical section at a time. The default lock is "unfair," meaning some threads might end up waiting longer than others, however, since my critical sections are very brief, this is acceptable. If fairness were required, I could use `new ReentrantLock(true)` instead.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |
| `list` and `map`: `add()`, `poll()`, `processOf()`, `snapshot()` | `queueLock` | many CPUs read and change the queue at the same time |
| `contextSwitchCount`: `incrementContextSwitch()`, `getContextSwitchCount()` | `contextSwitchLock` | read then write, an update can be lost |
| `completedProcessCount`: `incrementCompletedProcess()`, `getCompletedProcessCount()` | `completedLock` | if an update is lost the CPUs never stop and the watchdog fires |
| `totalServiceTime`: `addServiceTime()`, `getTotalServiceTime()` | `serviceTimeLock` | read then write, some time can be lost |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the original code, a CPU that finds the queue empty sleeps for 20ms before checking again, this happened 647 times during my run, which is a waste of processor time. In my implementation, the semaphore value represents the number of processes waiting in the queue. It is initialized to 0 (since the queue starts empty) and becomes 14 after the 14 processes are added in the `main` method. Now, a CPU becomes "blocked" when it calls `acquire()`, so it does not use the processor. Finally, the last CPU calls `release(totalCPUs)` to wake up the sleeping CPUs. If this step were omitted, they would stay asleep forever and the WATCHDOG would stop the program.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[This is a Producer-Consumer (or Bounded Buffer) problem. The "producer" is the `main` function when it initially adds processes, as well as the CPUs when they return a process that has not yet finished. The "consumer" is the CPUs when they take a process. Thus, the CPUs act as both a producer and a consumer.]

**Semaphores for a bounded queue (name and initial value)**:
[mutex = 1 to protect the queue. full = 0 for the number of processes in the queue. empty = K for the number of empty spaces.]

**Deadlock scenario and prevention**:
[If a producer acquires the mutex and then waits on the `empty` semaphore while the queue is full, the consumer will also need that same mutex to remove an item and free up space—resulting in a permanent deadlock. The solution is to break the "Hold and Wait" condition: we wait on the semaphore *before* acquiring the mutex. This is exactly what I did in my code—calling `acquire()` outside of `queueLock`.]

## Summary

**Key concepts I understood through these questions:**
1.Race condition: If two threads modify the same variable simultaneously, one update will be lost.
2.Locking: Ensures only one thread can enter a critical section; the release of the lock should always be placed within a `finally` block.
3.Semaphore: Allows the CPU to "sleep" until an operation is ready, rather than having it constantly check (poll) for updates.

**Concepts I need to study more:**
1.Fairness in locks, and when to use `ReentrantLock(true)`.
2.Solving the bounded buffer problem using three semaphores.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
