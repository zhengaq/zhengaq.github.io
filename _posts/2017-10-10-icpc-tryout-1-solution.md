---
layout: post
title:  "2017 UIUC ICPC Tryout 1 Solutions"
date:   2017-10-10 16:50:00 -0400
tags: editorials icpc
---


## Problemset

The problemset is available [here](/files/uiuc_2017_tryout_1.pdf)

## Solutions

### Problem A. Jumbled Compass

This is a similar problem to ```A + B```. You just need to compare two directions and take the better one.

Pay close attentions to the following special case mentioned in the output section.

- If the two input numbers are diametrically opposed, the needle should travel clockwise. 
- I.e., in this case, output 180 rather than 180.

### Problem B. Game Rank

This is a simulation problem. Read the problem carefully and do exactly what you are required to do. Note that ```If a player on rank 1 -- 20 loses a game, she loses a star. ``` means you will not lose any star if your rank is greater than 20. 

For simulation problem, I strongly recommend you to take notes for every important rule and then organize them into your own logics before you start to write the code. Otherwise, you may get stuck because of some missed rule. 

### Problem C. Islands

In this problem, we want to flip some cloud cells (i.e., C) into land cells (i.e., L) such that the number of connected components of land cells (i.e., islands) is minimized.

We have the following two observations:

- First of all, the upper bound of the answer is easy to obtain. Simply let C's be water cells (i.e., W). Then, we can compute the number of islands via breath-first search (BFS).
- Second, suppose there are two components and they can be connected through some C's (previously, we suppose they are W's). In this case, flipping these C's to L's will reduce the answer by 1. This part can be also done by BFS.

As a result, we have a greedy algorithm as follows.

1. Find all connected components (via L) of the current L's using BFS. This part is \\(O(n^2)\\).
2. Treat the components in Step 1 as nodes, find the connected components (via C) again using BFS. This part is also \\(O(n^2)\\).
3. The answer is the number of components in Step 2.

In fact, we can combine these two BFSs. Every time, we start from a L cell (not visited before) and expand via both L and C as far as possible. This is equivalent to the previous 2-stage BFS.


### Problem D. Bless You Autocorrect!

This problem has an important condition as the following. It puts the constraint on the total lengths of the dictionary.

- The dictionary and the words to type only use lower case letters ‘a’-‘z’. 
- The total size of the input file is at most 1 MB.

It reminds us again that important conditions may be hidden in the Input/Output sections.

The solution is as follows.

- First, let's construct a Trie for all input words. On each node, we can also store the most common word (denoted as \\(complete[u]\\) for node \\(u\\), which is also a node id in the Trie). This can be easily achieved by assigning the word to the newly created node because the input words are already ordered from the most common to the least common.
- Second, let's use the nodes in the Trie as the state for the dynamic programming. We use \\(f[u]\\) to denote the minimum number of keystrokes to reach the node u. Based on the statement, we have the following transitions.
    - Press the tab. Then, we can use \\(f[u] + 1\\) to update \\(f[complete[u]]\\).
    - Press the backspace. Then, we can use \\(f[u] + 1\\) to update \\(f[parent[u]]\\).
    - Press some real keys. Then, we can use \\(f[u] + 1\\) to update \\(f[child_{u, 1}], f[child_{u, 2}], \ldots , f[child_{u, k}]\\).
- Obviously, the initial state is that \\(f[root] = 0\\).

It's a little hard to figure out the order of these states. However, if we take a closer look at this dynamic programming, it is actually a shortest path problem. Moreover, the edge weights are always 1. Therefore, we can apply a simple BFS to address this problem. The final time complexity is \\(O(\mbox{the total length of the input words})\\).


### Problem E. Paint

This is an easy DP problem as long as you noticed that ```However, they don’t like each other, and each painter will only paint their given portion of the fence if no other painter overlaps their portion.```. It's equivalent to finding some intervals without overlaps but maximize the coverage.

Although the intervals may span over \\([1..10^18]\\), there are at most \\(2k\\) important points, which are the ends of the k input intervals. We sort these unique, important points and store them as \\(x[1..m]\\). Use \\(f[i]\\) be the maximum coverage if we only considering \\(1..x[i]\\). There are two choices if we want to use f[i] to update something else.

  - If we have some interval covers \\(x[i + 1]\\) to \\(x[j]\\), we can then use \\(f[i] + x[j] - x[i + 1] + 1\\) to update \\(f[j]\\).
  - We can always use \\(f[i]\\) to update \\(f[i + 1]\\).

As any interval from \\(x[i]\\) to \\(x[j]\\) will be only used once when using \\(f[i - 1]\\) to update \\(f[j]\\), thus, the time complexity is \\(O(k)\\).


### Problem F. Exponial

To solve this problem, you should know the following theorem.

\begin{equation}
x ^ y \equiv x ^ {y\ mod\ phi(m) + phi(m)}\ (mod\ m)
\end{equation}

where \\(phi(m)\\) is the [Euler's totient function](https://en.wikipedia.org/wiki/Euler%27s_totient_function), which is the number of integers between \\(1\\) to \\(m\\), which are co-primed to \\(m\\).

The following one is more famous but only holds when \\(gcd(x, m) = 1\\). Two contestants tried to applied this formula but failed to generalize it as the above.
\begin{equation}
x ^ y \equiv x ^ {y\ mod\ phi(m)}\ (mod\ m)
\end{equation}

Therefore, we can simplify the problem recursively.

\begin{equation}
f(n) \equiv n^{f(n - 1)} \equiv n^{f(n - 1)\ mod\ phi(m) + phi(m)}\ mod\ m
\end{equation}

It reduces the problem to ```f(n - 1) mod phi(m)``` from ```f(n) mod m```.

Another important observation is that 

```
phi(... phi(phi(m)) ... ) approaches to 1 very soon.
```
Therefore, the recursion will be ended very soon.


### Problem G. Artwork

This is a very classical application of the union-and-find set.

The problem looks like a divid-and-find set because it keeps separating things. However, if we first load all operations and apply all of them. And then, roll back to the beginning step-by-step. It immediately becomes a union-and-find set problem.

For many "offline" problems, thinking about the reserved order is always helpful.

### Problem H. Card Hand Sorting

This problem needs bruteforce + dynamic programming. Since the order of suits and the direction (i.e., increasing or decreasing) within each suit are not determined yet, we can first spend \\(4! * 2^4\\) to enumerate them.

After the enumeration, we know the full order of all cards. Then, this problem is the same as the longest increasing subsequence (LIS) problem, which is a classical DP problem. If you don't know how to solve it, please [Google it](https://stackoverflow.com/questions/2631726/how-to-determine-the-longest-increasing-subsequence-using-dynamic-programming).

### Problem I. Illumination

This is a 2-SAT problem. It's almost the same as the 2-SAT problem in our last year's regional contest. Unfortunately, no one accepted this problem. 

The basic ideas are as follows

- For each lamp i, we create two nodes ROW(i) and COL(i), which mean the lamp i is illuminating its row or column respectively.
- If two lamps i and j are located at the same row, then, we add a directed edge from ROW(i) to COL(j) and a directed edge from ROW(j) to COL(i). These two edges imply that if we choose ROW(i), we have to choose COL(j); And if we choose ROW(j), we have to choose COL(j). 
- Similarlly, if two lamps i and j are located at the same column, we add a directed edge from COL(i) to ROW(j) and a directed edge from COL(j) to ROW(i).

The feasibility can be determined by checking whether there is any conflict leading to that we have to choose ROW(i) and COL(i) simultaneously. To check this, we can apply the strongly connected component (SCC) algorithm (e.g., Tarjan's algorithm) to check whether ROW(i) and COL(i) are in the same SCC. If there is no such i, the solution should exist. Otherwise, there's no solution.

### Problem J. InTents

This is the hardest problem in this problemset. The expected solution looks like a search + pruning from my point-of-view. Also, basic 2D computational geometry is required. In the tryout, there's no one tried this problem.


### Problem K. Water

Simple max flow algorithms (like Ford-Fulkerson) can accept this problem. Some students tried to use Dinic. However, some bad Dinic implementation is really slow for dense graphs and thus getting Time Limit Exceeded. This is really unfortunate but a good lesson.

### Problem L. Barbells

This is a bruteforce enumeration problems. A few simple prunings should be enough.



