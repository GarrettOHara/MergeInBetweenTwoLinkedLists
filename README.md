# MergeInBetweenTwoLinkedLists
This is the source code to a medium level difficutly LeetCode quesiton. It was a recent favorite of mine.

## Background
Linked Lists are typically not my favorite structure to work with so it suprised me that I came up with the solution
so quickly. The majority of my time was remembering how to set `list2` as the next node after the ath index of `list1`
because I work with linked lists the least. 

## Approach
The first part of the motivation is simple. Set a reference to the start of the list to return after modifying it.
Then you must iterate until the ath index of the `list1`.

I belive the "challenge" of this problem derives from maintaing list1 and skipping all the elements until the bth index. 
This is where I created an additional pointer of `list1` called `pointer` that was also iterating to the ath index. 
Then I subtracted a from b to allow me to iterate `pointer` until the bth index with a simple while loop that decremented
b and the condition stopped when b was 0.

At this index simply make the next node the head of `list2`. the next node in `pointer`

## Complexity
ALthough the complexity of the algorithmn I wrote was optimal, there are various other ways to acheive O(n).

## Alternative Approach
For example one could create a ListNode `pointer` that is a copy of `list1` to iterate at the beginning until 
the ath index. Then create a new ListNode called `end` and iterate until the bth index again. Now we can add 
all the nodes in `list2` to `pointer`by stating `pointer.next = list2`. Then iterate to the end of `list2`.

The only thing left is to set all the nodes after the bth index to the end of `list2`. We conviniently
have this index where `end` is located. After we add all the remaining nodes in `end` to `list2`, we are done modifying 
the list and can return `list1`.
