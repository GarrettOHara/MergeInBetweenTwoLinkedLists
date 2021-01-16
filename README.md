# MergeInBetweenTwoLinkedLists
This is the source code to a medium level difficutly LeetCode quesiton. It was a recent favorite of mine.

## Background
Linked lists are typically not my favorite structure to work with so it suprised me that I came up with the solution
so quickly. The majority of my time was remembering how to set `list2` as the next node after the ath index of `list1`
because I don't work with linked lists frequently. 

## Approach
The first part of the motivation is simple. Set a reference to the head of `list1` to return after modifying it.
I called this ListNode `res`. Then you must iterate until the ath index of the `list1`.

I belive the "challenge" of this problem derives from maintaing `list1` and skipping all the elements until the bth index. 
This is where I created an additional pointer of `list1` called `pointer`. `pointer` was also iterating to the ath index
concurrently with `list1` so they are at the same position.

I changed the value of b at the beginning of the algorithm by subtracting a from it. Then I iterated `pointer` until the 
bth index with a simple while loop that decremented b and the condition stopped when b was 0.

`list1` is still at the ath index so I can set the next node to the entire contents of `list2`. After this I iterated until
`list1` was null and made the next node equal to `pointer`, which was the rest of `list1` after the bth index.

The linked list is done being modified and I can return `res`.

## Complexity
ALthough the complexity of the algorithmn I wrote was optimal, there are various other ways to acheive O(n).

## Alternative Approach
For example one could create a ListNode `pointer` that is a copy of `list1` to iterate at the beginning until 
the ath index. Then create a new ListNode called `end` and iterate until the bth index again. Now we can add 
all the nodes in `list2` to `pointer`by stating `pointer.next = list2`. Then iterate to the end of `list2`.

The only thing left is to set all the nodes after the bth index to the end of `list2`. We conviniently
have this index where `end` is located. After we add all the remaining nodes in `end` to `list2`, we are done modifying 
the list and can return `list1`.
