```
struct ListNode dummy;
    dummy.next = head;
    struct ListNode *fast = &dummy;
    struct ListNode *slow = &dummy;

    // Advance fast pointer so that the distance between fast and slow is n+1
    for (int i = 0; i < n + 1; i++) {
        fast = fast->next;
    }

    // Move fast to the end, maintaining the gap
    while (fast != NULL) {
        fast = fast->next;
        slow = slow->next;
    }

    // Skip the next node
    struct ListNode *temp = slow->next;
    slow->next = slow->next->next;
    free(temp); // Free the removed node

    return dummy.next;
```