# Iteration

- Iteration in a directional data structure like a list, array, or string is a common pattern in Python.
- Constant space is used in the iteration pattern.
- One can access only the current element in the iteration pattern
- Once the direction is set, it is not changed during the iteration.

## One Pointer, Same Direction

```
---> Move pointer to the right 
<--- Move pointer to the left

```

## Two Pointer, Same Direction, Variable Speed
```
Slow and Fast pointers going in same direction
```
- Detecting a cycle in a linked list
- Finding the middle of a linked list
- Detecting a palindrome in a linked list
- Finding the start of a cycle in a linked list

## Two Pointer, Different Directions
```
<--- ---> Move pointers in opposite directions
```

## Three Pointers
- Reverse a linked list
```python
def reverse_linked_list(head):
    prev, current = None, head
    while current:
        next = current.next
        current.next = prev
        prev = current
        current = next
    return prev
```

## Three Pointers, Different Directions
- Three pointers moving in different directions
```
<--- ---> Move pointers in opposite directions
```


## N Pointer, N Directions
```
<--- ---> <--- ---> Move pointers in different directions
```

> [!CAUTION]
> Is this even possible?

