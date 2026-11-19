# CSA09 - Assignment 3: Exception Handling & Multithreading

- **Name:** Bala Ashwin R
- **Register number:** 1921260102
- **Java version:** OpenJDK 21 (any JDK 17+ works)

## Compile and run (every task)
```
cd QN
javac *.java
java <ClassName>        # e.g. java AtmSimulation
```
(Classes with several top-level classes, e.g. StorageDemo, must be compiled with javac, not run directly with `java File.java`.)
Q5 and Q6 "while->if" experiments: run `java SeatBookingUnsync` / `java TokenCounterIf` ten or more times (use a shell loop) and record results.

| Task | Programs | Result summary |
|------|----------|----------------|
| Q1 | AtmSimulation, UncaughtTrace, BroaderFirst, ErrorCodeVersion, CostBenchmark | 7 inputs hit 6 different paths, finally ran every time; broader-first catch does not compile; exception ~350x slower than an error code |
| Q2 | StorageDemo (TODO done), ExamPortal, StackTraceCost | Chained cause preserved; without cause getCause() is null -> NPE; stack-trace cost grows with depth |
| Q3 | ReportGenerator | Naive manual close leaks 2 handles on failure; finally and try-with-resources leak 0 |
| Q4 | StationThread, StationRunnable, RunVsStart, FinishOrder, Priorities, DaemonDemo, ExecutorVersion | Output order varies between runs; total always 70; executor time ~ n/p |
| Q5 | SeatBooking (TODO done), SeatBookingUnsync, SeatBookingRace, SeatBookingFixedDelay, Strategies | Synchronized always 10 seats; unsynchronized with widened window sold 11-16 |
| Q6 | TokenCounter (TODOs done), TokenCounterIf, TokenCounterTrace, WalletDeadlock, Q6Alternatives | Sum 210; `if` gives wrong sums; deadlock detected, lock ordering fixes it |
| Q7 | ResultProcessor, ParallelStreamFailure | Summary matches ground truth for 11-file and 10,000-file sets; pool 1/2/4/8 timings recorded |

Each QN folder also has `*.out.txt` logs. Add your own output screenshots to each folder.
