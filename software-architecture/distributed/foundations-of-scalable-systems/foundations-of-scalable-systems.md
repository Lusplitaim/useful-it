# Notes about '[Foundations of Scalable Systems](https://www.goodreads.com/book/show/61046500-foundations-of-scalable-systems)'

## What is scalability?
It defines a software system's capability to handle growth in some dimensions of its operations, like:
* The number of simultaneous users ir external requests the system can process;
* The amount of data a system can process and manage effectively;
* The ability to maintain a stable response time as the request load grows.

## Scalability Basic Design Principles
The basic aim of scaling a system is to increase its capacity in some application specific dimension.
To increase the system's throughput we usually use next principles: replication and optimization.
1. Replication. We basically replicate the software processing resources to provide more
capacity to handle requests and thus increase throughput.\
![alt text](increasing-capacity-through-replication.png)
2. Optimization. Often this means using more efficient algorithms, adding extra
indexes in our databases to speed up queries, or even rewriting our server in a
faster programming language.