# Leetcode-682.-Baseball-Game
# Description
You are keeping the scores for a baseball game with strange rules. At the beginning of the game, you start with an empty record.

You are given a list of strings operations, where operations[i] is the ith operation you must apply to the record and is one of the following:

An integer x.
Record a new score of x.
'+'.
Record a new score that is the sum of the previous two scores.
'D'.
Record a new score that is the double of the previous score.
'C'.
Invalidate the previous score, removing it from the record.
Return the sum of all the scores on the record after applying all the operations.

The test cases are generated such that the answer and all intermediate calculations fit in a 32-bit integer and that all operations are valid.

 # Solution
 You're keeping track of scores in a baseball game, but the scoring has unusual rules.

At the start, you have an empty score record.
You're given a list of operations — each operation is a string, and it tells you what to do.

An integer x.

Record a new score of x : '+'

Record a new score that is the sum of the previous two scores : 'D'.

Record a new score that is the double of the previous score : 'C'.

Invalidate the previous score, removing it from the record.

In order to solve question we will be using stacks , because all the operations include manipulating the previous elements .We are using a stack (i.e., a list where we only add/remove from the end) because of the last-in, first-out (LIFO) nature of the operations.

Example:

Input: ops = ["5","2","C","D","+"]

Output: 30

Explanation:

"5" - Add 5 to the record, record is now [5].

"2" - Add 2 to the record, record is now [5, 2].

"C" - Invalidate and remove the previous score, record is now [5

"D" - Add 2 * 5 = 10 to the record, record is now [5, 10].


"+" - Add 5 + 10 = 15 to the record, record is now [5, 10, 15].

The total sum is 5 + 10 + 15 = 30.

Example : 

Input: ops = ["1","C"]

Output: 0

Explanation:

"1" - Add 1 to the record, record is now [1].

"C" - Invalidate and remove the previous score, record is now [].

Since the record is empty, the total sum is 0.

 # Algorithm
 1. Initialise an empty stack.
 2. Use a for loop which loops through the array of operarions.
 3. Check if the operation is '+' or 'D' or 'C'.
 4. If the operation is '+' : Add the current and previous 2 elements .
 5. If the operation is 'D' : Remove the top element.
 6. If the operation is 'C' : Double the top element.
 7. Else: add the integer number to the stack .
 8. Return the sum of the stack .
# Complexity
a. Time complexity

Loop runs once for each operation → O(n)

Each operation (+, D, C, number) takes O(1) time

sum(stack) at the end takes O(n) in the worst case

Total: O(n)

b. Space Complexity

Stack stores all valid scores

In the worst case, no scores are removed

Total space used: O(n)

Where n = number of operations in the input list.
