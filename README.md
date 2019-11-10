# CAP Theorem
This project has some examples of the CAP theorem

# Examples

## AP - Availability and Partition tolerance

![Screenshot](availability_partition_tolerance.png)

## CP - Consistency and Partition tolerance

![Screenshot](conistency_partition_tolerance.png)

## But Never Both (CA - Consistency and Availability) 

*You cannot, however, choose both consistency and availability in a distributed system.*

As a thought experiment, imagine a distributed system which keeps track of a single piece of data using three nodes—AA, BB, and CC—and which claims to be both consistent and available in the face of network partitions. Misfortune strikes, and that system is partitioned into two components: \lbrace A,B \rbrace{A,B} and \lbrace C \rbrace{C}. In this state, a write request arrives at node CC to update the single piece of data.

That node only has two options:

Accept the write, knowing that neither AA nor BB will know about this new data until the partition heals.
Refuse the write, knowing that the client might not be able to contact AA or BB until the partition heals.
You either choose availability (Door #1) or you choose consistency (Door #2). You cannot choose both.

To claim to do so is claiming either that the system operates on a single node (and is therefore not distributed) or that an update applied to a node in one component of a network partition will also be applied to another node in a different partition component magically.
