# Data Structure and Algorithms

Taking a look at this fundamental skillset for software devs.

## Watch

- [Basic Recursion](https://www.youtube.com/watch?v=vPEJSJMg4jY)
- [Data Structures in 15 Minutes](https://www.youtube.com/watch?v=sVxBVvlnJsM)
- [Big O Explained](https://www.youtube.com/watch?v=v4cd1O4zkGw)

## Read

[Basic Data Structures](https://towardsdatascience.com/8-common-data-structures-every-programmer-must-know-171acf6a1a42)
[Why Big O](https://web.archive.org/web/20230207075759/https://triplebyte.com/blog/why-you-should-learn-big-o-and-stop-hacking-your-way-through-algorithms)

## Discussion Questions

**What is 1 of the more important things you should consider when deciding which data structure is best suited to solve a particular problem?**

>*Some data structures are better suited than others for data manipulations. Per the Data Structures in 15 Minutes video linked cited above:*

- *linked lists are made of nodes comprised of values and pointers, which are oriented head-to-tail... they are good for adding and deleting data elements, but not retrieving, because each node is only aware of adjacent nodes.*

- *arrays are good for retrieving elements, but can be ineffcient in lower level languages due to the need to declare array lengths.*

- *hash tables (also known as dictionaries in Python) can retrieve values if given a key via a hashing fiunction. This can be used to efficiently find memory locations anywhere independent of the size of library. However, they are prone to comethign called key collisions were two key hashes occupy the same memory location*

- *stacks & queues are efficient line ups of information. Stack use a last in, first out protocol via push and pop methods using a call stack. Queues use a first in, first out protocol. The restrictions on data retrieval make these data structures have limited uses.*

- *graphs and trees are similar to nodes, but less linear with "edges" that point to each other. A tree is a heirarichal type of graph.*

**How can we ensure that we’ll avoid an infinite recursive call stack?**

>*We must tell the function when to stop running by using a base case (conditional) where the function no longer calls itself*

## Things I want to know more about

>*Graphs sound interesting... I'm sure we'll get our chance to learn more soon, though.*
