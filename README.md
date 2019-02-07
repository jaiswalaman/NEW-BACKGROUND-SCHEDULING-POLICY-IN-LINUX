# CSN-232-NEW-BACKGROUND-SCHEDULING-POLICY-IN-LINUX
To modify the Linux scheduler to implement a new scheduling class, called background scheduling. We will evaluate how our new scheduling class performs.We need to add a new scheduling policy called SCHED_BACKGROUND. This policy is designed to support processes that only need to run when the system has no other process to do.
When there are no processes which are managed by the SCHED_OTHER, SCHED_RR or SCHED_FIFO classes, our SCHED_BACKGROUND policy will run the background processes.
 When there is more than one SCHED_BACKGROUND process ready to run, they should compete for the CPU as do SCHED_OTHER processes using CFS i.e., ‘Complete Fair Scheduling’.
 We will implement a new policy SCHED_BACKGROUND to handle background tasks with lower priority than SCHED_IDLE. This will handle tasks only if queues of all other policies are empty.
