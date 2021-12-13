# Class 36

## <ins>*DSA Review*

Whiteboard-style interviews

- Restate the Question : (visualize) 

reestating the question to the interviewer shows that i understand the problem and if i have any misunderstanding the interviewer can correct it and it can make it more clear to step in and start solving the problem.

for example : given the head of a sorted linkedlist , delete all duplicates and return the linkedlist sorted.

Re-estating would be like : 

So the parameter for the function will be the head of a linked list and the output should be that linked without duplicate nodes.

- Ask about the test cases and the data types

- Ask About Edge Cases
    - the given head is for an empty linked list 
    - the given head is for linked list with one node

- Write the algorithm step by step 

    - create a function that takes sorted linked list head as input 
    - check if the head is null or head.next is null then return the head
    - define a prev pointer that will point to the head
    - define current pointer that will point to the head.next
    - traverse the linkedlist nodes while current is not empty
    - check if the current value is not equal to the previous value 
        - true :
            - set the previous next pointer to the current
            - set the previous node to be the current
        
        - set the current to the current.next
        - set the previous next pointer to None.

        - Return head


- Write Pseudocode :

```pseducode
ALGORITHIM remove_duplicates(head){
//input <-- linked list head

    if head = NULL and head.next = NULL
        RETURN head

    DEFINE prev <-- head
    DEFINE current <-- head.next

    while current != Null
        if current.value != prev.value
            prev.next = current
            prev = current
        current = current.next
        prev.next = NULL
    
    RETURN head
}
```
- Write the code 

```py 

def remove_duplicates(head):
    if not head or not head.next:
        return head

    previous = head
    current = head.next

    while current:
        if current.value != previous.value:
            previous.next = current
            previous = current
        current = current.next
        previous.next = None

    return head
```

- if any where in the steps felt like stuck , ask for help and ask to make things more understandable ( meaningfull questions )

