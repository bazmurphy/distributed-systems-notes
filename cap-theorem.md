# CAP Theorem

![](/images/cap-theorem-01.png)

The CAP theorem, is a concept in distributed computing that outlines the trade-offs between three crucial properties—Consistency, Availability, and Partition Tolerance.

The CAP theorem asserts that, in a distributed data store, **it is impossible to simultaneously guarantee all three of the following**:

1. Consistency

   - Every read operation in the system returns the most recent write. In other words, all nodes in the system have the same data at the same time.

   - Every client views the same data. Every node in distributed cluster recieves same data

2. Availability

   - Every request to the system receives a non-error response, without any guarantee that it contains the most recent write. The system remains responsive even in the face of failures.

   - During node failure time, every node must respond in a reasonable amount of time.

3. Partition Tolerance

   - The system continues to operate despite the loss of messages or network partitions, ensuring that each node can operate independently.

   - Guarantees partition tolerance can recover from partitions once the partition heals.

In a distributed system, network partitions (communication breakdowns between nodes) are inevitable.

The CAP theorem acknowledges that, during a network partition, **a choice must be made between providing consistency or availability.**

This led to the famous saying that in the event of a network partition, a system can either be **"consistent and partition-tolerant (CP)"** or **"available and partition-tolerant (AP)."**

The CAP theorem is a fundamental principle in designing and understanding distributed systems, influencing architects and engineers in making decisions about system trade-offs based on the specific requirements and priorities of their applications.
