# CLRS Ch. 1: The Role of Algorithms in Computing

# Algorithms

- Algorithm = a well-defined computational procedure that takes input and produces output
- Can be thought of as a transformation from input to output
- Algorithms are tools to solve a well-defined computational problem, which is defined in terms of the desired input and output
- A classic computational problem, which is fundamental to computer science:

**The Sorting Problem**
*Input:* A sequence of $n$ numbers $\langle a_1, a_2, \dots,a_n\rangle$.
*Output:* A permutation of the input sequence $\langle a_1', a_2',\dots ,a_n'\rangle$ such that $a_1' \leq a_2' \leq \cdots\leq a_n'$.

- A particular input to a problem is called an instance to the problem
- Correct algorithm = an algorithm that halts with the correct output for every instance of the input (i.e. it solves the problem correctly)
- An incorrect algorithm may be useful too—if we can control its error rate
- Algorithms can solve a variety of problems, from packet routing to resource optimization
- This text also discussed *data structures*, ways for storing and organizing data to make access and modification efficient
    - Each DS has its own tradeoffs
- There is not always a well-defined existing algorithm for a problem, which is when you should use techniques to design and analyze your own algorithms
- There is a special class of problems called *NP-hard* problems for which no efficient (polynomial time) solution exists
    - Recognizing NP-hard problems will save you time when trying to solve problems in the real world
- Parallelism of algorithms is key on modern processors with multiple cores

# Algorithms as a technology

- Studying algorithms is still important, even if speed and memory are not constrained, because you need to prove your algorithm is *correct*
- Algorithms to solve problems can vary in efficiency
    - For example, insertion sort takes O(n^2) time to sort n items, while merge sort takes O(n log n ) time to sort n items
    - You want to use algorithms whose running time grows slowly as a function of the input
- Algorithms, like computer hardware, should be treated as a technology
- Having a solid understanding of algorithms and their usage separates the truly skilled programmers