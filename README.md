<html>
<head></head>
<body>

<br>
<marquee><img src = "http://code.emc.com/images/code_icon.png"></marquee>
<b><br>Hello world!<br>My name is Amulya Gaur. I am pursuing B.Tech CSE from MNNIT Allahabad. This website is devoted to my projects in various domains of computer science. I hope you will definitely find them useful.<br></b>

Keep Coding! Have Fun!<br>
<br>
Contact:<br>
E-mail : amulyagaur111@gmail.com<br>
Facebook : https://www.facebook.com/amulya.gaur
<br>

<p style="text-align: left;"><strong>Prerequisites : Knowledge of C++ ,concept of pointers and time complexity analysis.</strong></p>
<p style="text-align: left;">Hello Coders</p>
<p style="text-align: left;">This article will introduce you to the world of Data Structures.It introduces the basic structures and techniques for building linked lists with a mixture of explanations, drawings, sample code, and exercises. The material is
useful if you want to understand linked lists or if you want to see a realistic, applied
example of pointer-intensive code.</p>
<p style="text-align: left;">Linked lists are useful to study for two reasons:</p>

<ul>
	<li style="text-align: left;">Most obviously, linked lists are a data structure which you may want to use in real programs. Seeing the strengths and weaknesses of linked lists will give you an appreciation of the some of the time, space,and code issues which are useful to thinking about any data structures in general.</li>
	<li>Linked list problems are a nice combination of algorithms and pointer manipulation.</li>
</ul>
<strong>Why linked lists?.. Why not arrays?</strong>

In most languages, arrays are convenient to declare and the provide the handy [ ] syntax to access any element by its index number.

For example : In C++, one may declare it like
<code>int arr[100];</code>

This will allocate a continuous block of memory at the compile time.

Or it can be declared during runtime as follows.
<code>int *arr = new int[100];</code>

This will again allocate a continuous block of memory. But memory will be allocated in the heap section during runtime. But still, once declared the size of the array remains fixed. It can’t be altered dynamically.

The disadvantages of arrays are...
<ul>
	<li>The size of the array is fixed — 100 elements in this case. You can go to the trouble of dynamically allocating an array in the heap and then dynamically resizing it with realloc(), but that requires some real programmer effort.</li>
	<li>Because of (1), the most convenient thing for programmers to do is to allocate arrays which seem "large enough" . Although convenient, this strategy has two disadvantages:(a) Most of the time there are just 20 or 30 elements in the array and 70% of the space in the array really is wasted.(b) If the program ever needs to process more than 100 scores, the code breaks.</li>
	<li>Inserting new elements at the front is potentially expensive because existing elements need to be shifted over to make room. This requires O(n) time for completion where n is the size of the array.</li>
</ul>
<img class="irc_mi" src="http://www.stoimen.com/blog/wp-content/uploads/2012/06/0.-Arrays-vs.-linked-list.png" alt="Image result for linked list" width="621" height="333" />

The above picture clearly demonstrates the difference between the two data structures. Now without any further jargon ,lets dive into the beautiful world of linked lists.

Linked lists have their own strengths and weaknesses, but they happen to be strong where arrays are weak.As we will see, linked lists allocate memory for each element separately and only when necessary. So their size can be altered dynamically.

<strong>What Linked Lists Look Like?</strong>

An array allocates memory for all its elements lumped together as one block of memory.

In contrast to an array, a linked list allocates space for each element separately in its own block of  memory called a "linked list element" or "node". The list gets is overall structure by using  pointers to connect all its nodes together like the links in a chain.

Each node contains two fields: a "data" field to store whatever element type the list holds for its client, and a "next" field which is a pointer used to link one node to the next node. Each node is allocated in the heap with a call to new function in C++, so the node memory continues to exist until it is explicitly deallocated with a call to free(). The head of the list is a pointer to the first node. Last node of the linked lists points to NULL which indicates the end of the list.

<img class="irc_mi" src="http://www.penguinprogrammer.co.uk/images/data-structures/single-list.png" alt="Image result for linked list" width="527" height="222" />

We always keep with us a pointer to the first node of(also called Head Node). This pointer is very essential as this is the only identity of the linked list.

Now lets see some real code for building and manipulating linked lists..
<ul>
	<li>Structure of Linked Lists</li>
</ul>
https://gist.github.com/amulyagaur/502d42e56844a7df9a6862c0cb8f83fb
<ul>
	<li>Inserting nodes :</li>
</ul>
https://gist.github.com/amulyagaur/274c355115114ddb0ef3ea7a2f1bc15b

This function takes the head pointer as an argument and inserts a new node at the beginning of the list.

Time Complexity: O(1)

Suppose the list is currently 4->5->7 , and user wants to insert a node of value 6. So the first step will be to <span class="pl-c">dynamically allocate a new node</span> in the heap section and set the data and the link part as required. The new node will be the head node, the link part will be set as head, and the address of new node will be stored in head.

A similar function to insert at tail is given below:

https://gist.github.com/amulyagaur/9f22ba4ca4c570ce42f882ad369d333b

This function will create a new node and set its link part as NULL(this node will be the tail node). Then the link part of the previously last node will be set as the address of the new node.

Time Complexity: O(n) , n=size of list.

What about inserting at a specific position?

https://gist.github.com/amulyagaur/f5b16f6b38e7f3a6c28fa7586097e68e

I'm leaving the analysis of this function as an assignment to the reader. :)

Time Complexity: O(n) in the worst case when we have to insert at the last position.
<ul>
	<li>Printing the elements of the list</li>
</ul>
The main idea for this task is to iterate the head pointer till it reaches the end of the list.

https://gist.github.com/amulyagaur/8b5f9653bcb8719b6d0c3e73ca5e399c

Time Complexity: O(n)

I urge you to write a recursive implementation of the print function as an exercise.

So  now we have the required tools to build and print a linked list. Here we go for the complete program.

https://gist.github.com/amulyagaur/a7443423f84cc7970579ae46685bd4a1

There is a lot to talk about in Linked Lists which will be covered in future posts.

Thanks for reading....

Happy Coding! :)
