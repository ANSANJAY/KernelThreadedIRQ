Why is the threaded handler not being executed even after thread is created?
=============================================================================

Why is the threaded handler not being executed even after thread is created?
=============================================================================

When the hard-IRQ handler (handler function) function returns IRQ_WAKE_THREAD, 

the kthread associated with this bottom half will be scheduled, invoking the thread_fn

The thread_fn function must return IRQ_HANDLED when complete.

After being executed, the kthread will not be rescheduled again until the IRQ is triggered again and the hard-IRQ returns IRQ_WAKE_THREAD
