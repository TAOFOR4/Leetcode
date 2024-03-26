```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */

struct ListNode* reverseList(struct ListNode* head) {
    struct ListNode *prev = NULL, *current = head, *nextNode = NULL;
    while (current != NULL) {
        nextNode = current->next; // Save next
        current->next = prev; // Reverse current node's pointer
        prev = current; // Move pointers one position ahead.
        current = nextNode;
    }
    return prev;
}

bool isPalindrome(struct ListNode* head) {
    if (head == NULL || head->next == NULL) return true;
    
    struct ListNode *slow = head, *fast = head;
    // Find the middle
    while (fast->next != NULL && fast->next->next != NULL) {
        slow = slow->next;
        fast = fast->next->next;
    }
    
    // Reverse the second half
    slow->next = reverseList(slow->next);
    slow = slow->next;
    
    // Compare the first and second half nodes
    while (slow != NULL) {
        if (head->val != slow->val) return false;
        head = head->next;
        slow = slow->next;
    }
    
    // Optional: Restore the list (reverse the second half back)
    
    return true;
}
```