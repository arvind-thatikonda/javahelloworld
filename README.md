----------------------
Command Line Arguments
----------------------

Example:  ./word-count -b -sort SelectionSort -suf < textfile

-b | -a | -s
  (required) Specifies the type of tree for storing (word, count) pair
  possible trees are Binary search tree, Avl tree, and Splay tree

    -b - Count frequencies using an unbalanced binary search tree 
    -a - Count frequencies using an AVL tree 
    -s - Count frequencies using a splay tree 

-sort SelectionSort | MergeSort | HeapSort
  (optional) Specifies the type of sort.  
  If -sort is omitted, HeapSort is used

-suf
  (optional) Turns on suffix checker

-------------------------
Design Decisions & Issues
-------------------------
Since we stereotype against english majors, let's avoid writing this in an
essay format...

Q.  The original BinarySearchTree::Insert() resolves key collosion by
overwriting the old value with the new value.  How does the modified insert
functions resolve key collosions?

A.  The modified insert functions resolve key collosions by adding the new
value to the old value.  For example, if there exists a key K with a value 3,
and we wanted to insert a key K with value 2, the Insert function would change
the value to 3+2=5.  For our word-count, every key is inserted with a value 1.
However, it's easy to see that the insert functions allow different changes to
be made to the existing key-value tree.
    Consequently, the + operator must be overloaded for the ValueType.  
