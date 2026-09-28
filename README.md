# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each. 

1. $T(n)$ is $\mathcal{O}(n^2)$.
-  This can be either true or false. This can be true because T(n) at it's worst is $\mathcal{O}(n^2)$ which is equal to $\Omega(n^2)$, but it can also be false because T(n) can be better than $\mathcal{O}(n^2)$
2. $T(n)$ is $\Theta(n^3)$.
- This is true because T(n) is absolutely n^3, which is equal to our worst case scenario of $\mathcal{O}(n^3)$
3. $T(n)$ is $\Omega(n)$.
- This is true because T(n) is always in the range of n^2 and n^3 which means that it will always run worse than the best case of n
4. $T(n)$ is $\Theta(n^{1.5})$.
- This is false because $\Theta(n^{1.5})$ states that the actual running time is n^1.5 which is worse than our best running time of n^2
5. $T(n)$ is $\mathcal{O}(n)$.
- This is False because the best case running time is n^2 steps, but $\mathcal{O}(n)$ says the worst case running time is n steps which is a contradiction
6. $T(n)$ is $\Theta(n^2 \log n)$.
- This could be true because $\Theta(n^2 \log n)$ is within the bounds of n^3 and n^2. This could also be False because the actual running time could not be $\Theta(n^2 \log n)$ and it could instead be something else within the bounds.


## Problem 2
Consider the following algorithm where $f(A, i, j)$ is an unknown algorithm that takes as input an array $A$ and two indicies $i$ and $j$ and returns a number. 

```
Mystery Algorithm
Input: An array of int $A$ of length $n$.
Output: int sum
    n = |A|
    sum = 0
    for i = 1 to n:
        for j = 1 to n:
            sum += f(A, i, j)
```

Without knowing anything about $f$, what can we say about the running time of the Mystery Algorithm in terms of $n$? Justify your answer. 

We have 3n^2+2

By dropping constants and using the sum is max property, we get O(n^2). But we have to include the running time of the algorithm $f(A, i, j)$. The running time of this algorithm could be anything between 1 and infinite steps. 