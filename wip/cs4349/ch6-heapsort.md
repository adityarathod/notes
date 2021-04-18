# Heapsort
- Combines the best of merge sort and inseration sort:
  - $O(n \log n)$ worse case – like merge sort
  - Sorts in place – like insertion sort
- Uses a **heap**

## Heap (Data Structure)
- An array that is nearly a complete binary tree
- Each node of the tree is an element of the array
- The tree is filled on all levels except maybe the lowest, which is filled from the left up to a certain point
- An array `A` that represents a heap is an object w/ two attributes:
  - `A.length` = the number of elements in the array
  - `A.heap_size` = the number of elements in the heap that are stored in `A`. (can be ≤ length of array)

### Heap Example
- `A[0]` is the root of the tree
- Given index _i_ of a node, its parent, left child, and right child are retrieved as follows:

```python
parent = lambda i: floor(i/2)
left = lambda i: 2i
right = lambda i: 2i + 1
```

## Heap Properties
- **Max-heap property**
  - For all nodes $i$ (excluding the root), `A[parent(i)] ≥ A[i]`.
  - Largest element at root
  - The heapsort algorithm uses max-heaps.
- **Min-heap property**
  - For all nodes $i$ (excluding the root), `A[parent(i)] ≤ A[i]`.
  - Smallest element at root

## Maintaining the Heap Property: Max-Heapify
- Algorithm that is used to maintain the max-heap property.
- Before this algorithm, `A[i]` may be smaller than its children.
- Assume left and right subtrees of $i$ are max-heaps
- After max-heapify, subtree rooted at $i$ will be a max-heap
- Method:
  - Compare `A[i]`, `A[left(i)]`, and `A[right(i)]`
  - If necessary, swap `A[i]` with the larger of the two children to preserve heap property
  - Continue until the subtree rooted at $i$ is a max-heap.
- Recurrence for running time: $T(n) = T(\frac{2n}{3}) + \theta(1)$
  - Overall running time: $O(\log n)$

```python
def max_heapify(A, i, n):
  l = left(i)
  r = right(i)
  largest = None
  if l <= n and A[l] > A[i]:
    largest = l
  else:
    largest = i
  if r <= n and A[r] > A[largest]:
    largest = r
  if largest != i:
    A[largest], A[i] = A[i], A[largest]
    max_heapify(A, largest, n)
```

## Building a Heap
- `BuildMaxHeap(A,n)` produces a max-heap from an unordered array `A[0...n]` using the `MaxHeapify(A, i, n)` procedure in a bottom-up manner

```python
for i in reversed(range(floor(n/2))):
  max_heapify(A, i, n)
```

# Heapsort
- Uses a max-heap as a means to sort the array
- Complexity: $O(n \log n)$
- Place the max element into the correct place by swapping it with the element in the last position
- Decrease heap size and call `max_heapify()` on the remaining heap until the heap is of size 1

```python
def heapsort(A, n):
  build_max_heap(A, n)
  for i in reversed(range(1, n)):
    A[0], A[i] = A[i], A[0]
    max_heapify(A, 0, i - 1)
```

# Priority Queues
- A dynamic set that makes use of heap-order property to store an element-key pair