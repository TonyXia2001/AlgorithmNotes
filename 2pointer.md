# Two-Pointer Array Traversal

[TOC]

## Requirements

- The array needs to be sorted
- There's a target/pivot we want to compare with

## Basic Idea

- One pointer points at the left end, and the other pointer points at the right end.

- let's call the left pointer pointed value x, and the right pointer pointed value y.

- This technique is used when we want to traverse all the possible values of $f(x, y)$ and compare the output of $f$ with a target value $C$

    - $f(x, y) = x + y$,	$f(x, y) = x \times y,$	etc...

    - `[1, 2, 3, 7]`, what's the sum of two numbers that's closest to 6?

    - ```
        x		y		sum		comparison --->	action
        1		7		8		8 > 6			y-pointer--
        1		3		4		4 < 6			x-pointer++
        2		3		5		5 < 6			x-pointer++
        The two pointers hit, and thus the loop ends. The closest sum is 5.
        ```

- Pseudocode

- ```
    sort(arr)
    i = 0, j = arr.length - 1
    while i < j:
    	if f(arr[i], arr[j]) < target:
    		i++
        else if f(arr[i], arr[j]) > target:
        	j--
        else do stuff		// f(arr[i], arr[j]) == target
    ```

## Advantages

- $O(n)$ time instead of $O(n^2)$ (nested loop).

## Examples

- [3-sum](https://leetcode.com/problems/3sum/): find combinations of three numbers in an array that add up to 0
- [3-sum-close](https://leetcode.com/problems/3sum-closest/): find the closest three number sum to the target value
- [4-sum](https://leetcode.com/problems/4sum/): find the combinations of four numbers in an array that add up to `target`