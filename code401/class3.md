## Big O: Analysis of Algorithm Efficiency
* notation is used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors
* Big O Notation is all about the way an algorithm grows when it runs:

    * running time : how much time your code will take to complete.

    * memory space : how much your code will take space form the memory

* Units of Measurement.

     * The time in milliseconds from the start of a function execution until it ends
    * The number of operations that are executed
    * The number of “Basic Operations” that are executed

* In order to quantify Memory Space 
    * how much space the code will take
    * how much space for the input data
    * how much space needed for the out put data
    * how much space needed to hold calculation 

 * this is the type of the complixty 
 ![link](./class3Image/Screenshot%20(156).png)

   ![link](./class3Image/mypic.png)

* Review
* Big O: The worst case analysis of algorithm efficiency.
* Running Time: The amount of time required for an algorithm to complete.
* Memory Space: The amount of memory resources required for an algorithm to  complete.
* Input Size: Represented by the variable n, the total size of values used as parameters in an algorithm.
* Big Omega: The best case analysis of algorithm efficiency.
* Big Theta: The typical or random case used for analysis of algorithm efficiency.

## Linked Lists 
* in the first we have to know that  data structures, which are the different ways that we can organize our data; variables, arrays, hashes, and objects 
 *  Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.
 * difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures
  * the type of the linked list two type , singly linked , doubly linked and circular linked as shown 
  ![link](./class3Image/Screenshot%20(158).png)

  * how to add new node in the linked list 
    * First, we find the head node of the linked list.
    * Next, we’ll make our new node, and set its pointer to the current first node of the list.
    * Lastly, we rearrange our head node’s pointer to point at our new node.

  * Q ) question like, “Please tell me the how you’d implement X as a linked list, and what the possible drawbacks of that implementation are?”
