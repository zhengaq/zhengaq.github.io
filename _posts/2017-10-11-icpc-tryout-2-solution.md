---
layout: post
title:  "2017 UIUC ICPC Tryout 2 Solutions"
date:   2017-10-11 22:25:00 -0400
tags: editorials icpc
---

## Problemset

The problemset is available [here](https://open.kattis.com/contests/naq17open/problems)

## Acknowledgment

This editorial is mainly drafted by [Lan Dao](http://codeforces.com/profile/TiChuot97). I only wrote problem A and edit some format.

## A: Birthday Cake

First, you should know the Euler formula about the relation between the number of points, edges, and planes. Furthermore, there is a super important message in the Input section as follows.

- All candles and lines are distinct. 
- No candle is on a cut line. 
- No line is completely outside or tangent to the cake. 
- The input guarantees that the number of cake pieces remains the same if any cut line is shifted by at most \\(10^{−4}\\) in any direction. 
- The input also guarantees that each candle remains in the interior of the same piece of cake if its position is shifted by at most \\(10^{−4}\\) in any direction.

As a result, there will be no corner cases at all, especially there will be no three cuts intersecting at the same point, which is a really good news.

So, we can apply an \\(O(m^2)\\) bruteforce algorithm to compute the number of points (intersections) and the number of edges (segments). After that, using the Euler formula, we can get the number of planes (regions). If this number is not desired, we don't need to further check the positions of candles. 

The position of a candle can be uniquely identified by a \\(m\\)-bit mask: for each line, by plugging the candle coordinate into the line \\(ax+by+c\\) and check whether it is greater than \\(0\\). Therefore, to check whether each of those \\(n\\) regions contains exactly one candle, we can just check whether these masks are distinct.


## B: Bumbped
We first create a graph \\(G = (V, E)\\) where

* The set of vertices is
 \begin{equation}
  V' = \{ (u, x) | \forall 1 \leq u \leq n, x \in \\{0, 1\\} \}
 \end{equation}

* There is an edge from \\(u, x\\) and \\(v, y\\) in \\(E'\\) with cost \\(C\\) if and only if one of the following is true:
    - \\(x = y\\) and there is an a road connecting \\(u_{th}\\) city and \\(v_{th}\\) city. In this case \\(C\\) equals the cost to travel \\(u, v\\) road.
    - \\(x < y\\) and there is a flight from \\(u_{th}\\) city to \\(v_{th}\\) city. In this case \\(C = 0\\).

Let us denote \\(L((u, x), (v, y))\\) be the length of the shortest path from \\((u, x)\\) to \\((v, y)\\) in \\(G\\). Then, the answer to our original problem is 
 \begin{equation}
  min \\{ L((s, x), (t, y)) | \forall x, y \in \\{0, 1\\} \wedge x \leq y \\}
 \end{equation}

We can solve this by using Dijkstra algorithm on \\(G\\).

## C: Canonical Coin Systems
To solve this problem, we need to determine if there is a counterexample for the given system. We will use dynamic programming to answer this question.

Let \\(f(S)\\) be the minimum number of coins we need to form a sum of \\(S\\) using the given denominations. Then we have
 \begin{equation}
  f(S) = min\\{f(S - c_i) + 1 | 1 \leq i \leq n\\}
 \end{equation}

Let \\(g(S)\\) be the number of coins we need to form the sum of \\(S\\) using greedy algorithm. Then
 \begin{equation}
  g(S) = g(S - c_t) \textit{ where t is the maximum number such that \\(c_t \leq S\\)}
 \end{equation}

Then, a sum \\(S\\) is a counterexample if \\(f(S) \neq g(S)\\). Since we are already given a hint that the minimum counter example is at most \\(2c_n\\), we only need to compute \\(f(S), g(S)\\) for all \\(S \leq 2c_n\\). Thus, the complexity of the algorithm is only O(\\(nc_n\\)).

## D: Cat and Mice
Let \\((x_i, y_i)\\) and \\(s_i\\) be the coordinate of the \\(i_{th}\\) mouse and the time it stays above the ground. 
We also denote function \\(T(i, j, v) = \frac{\sqrt{(x_i - x_j)^2 + (y_i - y_j)^2}}{v}\\) be the amount of time to get 
from the \\(i_{th}\\) mouse to the \\(j_{th}\\) mouse with speed \\(v\\).


Suppose we have two real values \\(v_1, v_2\\) such that \\(v_1 < v_2\\) and we are able to get all the mice with initial 
speed \\(v_1\\), then clearly we can also achieve the same thing with initial speed \\(v_2\\). Similarly, if we can't get 
all the mice with initial speed \\(v_2\\), we certainly can't get all the mice with initial speed \\(v_1\\). With this 
property, we can binary search the minimum initial speed \\(v\\). Then, our problem becomes: Given an initial speed \\(v\\), 
determine whether we are able to get all the mice.


We will solve the new problem using dynamic programming. Let \\(f(S, i)\\) (where \\(S\\) is a subset of all mice and 
\\(i \in S\\)) be the minimum amount of time we need to get all the mice in set \\(S\\) and the last mouse we get is 
\\(i\\). We also denote \\(f(S, i) = -1\\) if there is no way to get all the mice in \\(S\\) with \\(i\\) be the last one. 
For the sake of our problem, we also denote \\(min\{\emptyset\} = -1\\). Let \\(x_0 = y_0 = 0\\), then our base cases will be
- If \\(T(0, i, v) > s_i\\), \\(f(\\{i\\}, i) = -1\\).
- Otherwise, \\(f(\\{i\\}, i) = T(0, i, v)\\).

And for all other cases
 \begin{equation}
  f(S, i) = min \\{ f(S', j) + T(i, j, v) | S' = S \setminus \\{i\\}, j \in S', f(S', j) \neq -1, f(S', j) + T(i, j, v) \leq s_i\\}
 \end{equation}

Then, we can get all the mice with initial speed \\(v\\) if there exists \\(i\\) (\\(1 \leq i \leq n\\)) such that 
\\(f(\\{1, 2, ..., n\\}, i) \neq -1\\).

## E: Company Picnic
Let us number the employees from \\(1 \to n\\) and let \\(s_i\\) be the running speed of the \\(i_{th}\\) employee. Let us
create a rooted tree \\(G\\) where each node represents an employee and node \\(i\\) is a parent of node \\(j\\) if the
\\(j_{th}\\) employee is the direct supervisor of the \\(i_{th}\\) employee. The root of the tree is the node representing
the CEO.

Suppose we have a value \\(v\\). If we know that there exists a formation which results in the average speed \\(v_a \leq v\\),
we know that the answer is at least \\(v\\). Otherwise, the answer cannot exceed \\(v\\). With this property, we can binary
search for the optimal average speed \\(v_{optimal}\\). Then, the remaining problem is to determine if we can form a set of
teams where the average speed is at least \\(v_{min}\\) for any given \\(v_{min}\\).


We will solve this problem using dynamic programming. Suppose we have a team formation with pairs \\((i_1, j_1), (i_2, j_2), ..., (i_k, j_k)\\).
Then, the average running speed of these teams is
 \begin{equation}
  \frac{\sum_{t = 1}^k min\\{s_{i_t}, s_{j_t}\\}}{k}
 \end{equation}
Let \\(T_{v_{min}}(i, j) = min\\{s_i, s_j\\} - v_{min}\\). Then we have
 \begin{equation}
  \frac{\sum_{t = 1}^k min\\{s_{i_t}, s_{j_t}\\}}{k} \geq v_{min} \iff \sum_{t = 1}^k min\\{s_{i_t}, s_{j_t}\\} \geq kv_{min} \iff \sum_{t = 1}^k (min\\{s_{i_t}, s_{j_t}\\} - v_{min}) = 
  \sum_{t = 1}^k T_{v_{min}}(i_t, j_t) \geq 0
 \end{equation}

Let us call the sum \\(\sum_{t = 1}^k (min\\{s_{i_t}, s_{j_t}\\})\\) the \\(T\\)-sum of this formation.


Let \\(f(u, p)\\) (\\(1 \leq u \leq n, p \in \\{0, 1\\}\\)) be the maximum number of teams can be formed using only employees 
represented by nodes under subtree rooted at \\(u\\) and \\(p\\) denotes whether we can pair \\(u\\) with one of its children
(\\(p = 1\\) means you can). Similarly, let \\(g(u, p)\\) be the maximum \\(T\\)-sum of all the formation with \\(f(u, p)\\) teams.
Lastly, let \\(better(u)\\) be defined as:

- If \\(f(u, 0) > f(u, 1)\\) or \\(f(u, 0) = f(u, 1) \wedge g(u, 0) > g(u, 1)\\), \\(better(u) = 1\\).
- Otherwise, \\(better(u) = 0\\).

Then, for each \\(u\\) we have:

- \\(f(u, 0) = \sum_{v \in children(u)} f(v, better(v))\\)
- \\(g(u, 0) = \sum_{v \in children(u)} g(v, better(v))\\)

To calculate \\(f(u, 1)\\) and \\(g(u, 1)\\), we will try to pair \\(u\\) with each of its child and take the maximum:

- \\(f(u, 1) = f(u, 0) + max\\{f(v, 0) - f(v, better(v)) + 1 \vert v \in children(u)\\}\\)
- \\(g(u, 1) = g(u, 0) + max\\{g(v, 0) - g(v, better(v)) + T_{v_{min}}(u, v) \vert v \in children(u)\\}\\)


Then, to determine if the minimum average speed is at least \\(v_{min}\\), we only need to check if \\(g(root, 0) \geq 0\\).

## F: GlitchBot
Since the constraints are relatively small, for each instruction, we can replace that instruction with \\(\textit{Forward/Left/Right}\\)
and the check if the new set of instruction is correct. We can verify if a set of instructions is correct by simulating the robot.
We stop as soon as we can find a good instruction set by replacing some instruction. Since we have \\(n\\) instructions and for each
instruction, the simulation process takes O(\\(n\\)), the total complexity is O(\\(n^2\\)).

## G: Greeting Card
We are given \\(n\\) points on an \\(xy\\)-plane. We are asked to count the number of pair of two points such that the Euclidean
distance between them is exactly 2018.


Suppose we have 2 points \\((x_1, y_1)\\) and \\((x_2, y_2)\\). Then
 \begin{equation}
  \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2} = 2018 \iff (x_1 - x_2)^2 + (y_1 - y_2)^2 = 2018^2
 \end{equation}

Since \\(x_1, x_2, y_1, y_2\\) are all integers, \\((x_1 - x_2)^2\\) and \\((y_1 - y_2)^2\\) are integers. The key
observation here is there are only 4 ordered pairs of integers \\((a, b)\\) such that \\(a^2 + b^2 = 2018^2\\). Those are
(0, 2018), (2018, 0), (1118, 1680), (1680, 1118).


Then, for each point \\((x, y)\\) among the \\(n\\) given points and each pair \\((a, b)\\) mentioned above, we will count
the number of points \\((x', y')\\) that:
 \begin{equation}
  |x - x'| = a \wedge |y - y'| = b
 \end{equation}
This can be done in several ways. One easy way to achieve this is that for each given point, we will store it inside a data
structure that allows fast query base on the coordinates (such as \\(\textit{std::set}\\) or \\(\textit{std::map}\\) in C++).
Since each pair of points would be counted twice this way, we need to divide our sum by 2 to get the desired answer.

## H: Imperfect GPS
Let \\(T\\) be the recording period of the GPS. For each time \\(t\\) which is a multiple of \\(T\\) and does not exceed \\(t_n\\) 
we will calculate the position of the runner. If \\(t = t_n\\), then the position recorded by the GPS at time \\(t\\) is \\((x_n, y_n)\\).
Otherwise, let \\(j\\) be the largest number between 1 and \\(n\\) such that the \\(t_j\\) is at most \\(t\\). Then, the position 
recorded by GPS at time \\(t\\) \\((x', y')\\) is:
 \begin{equation}
  x' = \frac{t - t_{j}}{t_{j + 1} - t_{j}}(x_{j + 1} - x_{j}) + x_j,
  y' = \frac{t - t_{j}}{t_{j + 1} - t_{j}}(y_{j + 1} - y_{j}) + y_j
 \end{equation}
To get the index \\(j\\) for each time \\(t\\), we can either use two-pointers technique or binary search for \\(j\\). With the 
recorded positions of the GPS, it should be easy to calculate the desired answer.

## I: Odd Gnome
Suppose we have \\(n\\) gnomes in line with indexes \\(a_1, a_2, ..., a_n\\). Then, if there exists index \\(1 < i < n\\) such that 
\\(a_i \neq a_{i - 1} + 1\\) and \\(a_i \neq a_{i + 1} - 1\\), then the \\(i_{th}\\) gnome is the king. Otherwise, if \\(a_1 \neq a_2 - 1\\)
then the \\(1_{st}\\) gnome is the king. Other than that, the last gnome is the king.

## J: Progressive Scramble
Suppose we have a string \\(s\\) with length \\(L\\):

- To encode \\(s\\) into \\(s'\\): \\(s'_0 = s_0\\) and \\(s'_i = v^{-1}\bigg(\Big(v\big(s_i\big) + v\big(s'\_{i - 1}\big)\Big)\bigg) 
\textit{ mod } 27\\) for all \\(1 \leq i \leq L\\)
- To decode \\(s\\) to get \\(s'\\): \\(s'_0 = s_0\\) and \\(s'_i = v^{-1}\Bigg(\bigg(\Big(v\big(s_i\big) - v\big(s'\_{i - 1}\big)\Big) 
\textit{ mod } 27 + 27\bigg) \textit{ mod } 27\Bigg)\\) for all \\(1 \leq i \leq L\\)

Where \\(v^{-1}\\) is the inverse function of \\(v\\).

## K: Space Probe
Notice that the product \\(nk \leq 10^7\\), for each measurements time \\(m_i\\) and prohibited segment \\([b, e]\\), we know that
the starting time cannot be between \\([b - m_i, e - e_i]\\). Therefore, we can obtain \\(nk\\) segments of starting time that are
"prohibited". Let us sort the beginning and the ending of all such segments. For points with the same magnitude, we break the tie
by prioritizing the beginning points. We will then perform sweep line algorithm on the sorted points and keep track of the "opening" 
segments at each point. Let \\(l, count\\) all initially equals to zero. Then, we iterate through the sorted points in order. For
a point \\(x\\):

- If \\(x\\) is a closing point: We decrease the value of \\(count\\). If \\(count = 0\\), we assign \\(l = x\\).
- If \\(x\\) is a beginning point: We increase the value of \\(count\\). If \\(count = 1\\), let \\(L = max(t_1, l), R = min(t_2, x)\\).
If \\(L > R\\), we can go to the next point. Otherwise, \\([L, R] = [t_1, t_2] \cup [l, x]\\). Then, we know for sure that it is safe to 
start the process anytime in between \\((L, R)\\). Thus, we add \\(\frac{R - L}{t_2 - t_1}\\) to the result.

After iterating over all points, we can do similarly to the second case with \\(x = t_2\\). Then, we will have our final result.

## L: Suspension Bridges
We have
 \begin{equation}
  a + s = a \cdot \cosh\bigg(\frac{d}{2a}\bigg) \implies s = a \cdot \cosh\bigg(\frac{d}{2a}\bigg) - a
 \end{equation}

Noticing that the function \\(s(a)\\) is decreasing, we can binary search for the right value of \\(a\\). With such value,
we can easily calculate the required result.

## M: Umbral Decoding
Suppose we have a safe point \\((x, y, b)\\) and a point \\((p, q)\\) that lies inside the umbra of the given safe point. Then
 \begin{equation}
  |x - p|^3 + |y - q|^3 \leq b \implies |x - p|^3 \leq b \implies |x - p| \leq \sqrt[3]{b}
 \end{equation}
Similarly, we have \\(|y - q| \leq \sqrt[3]{b}\\). We also know that \\(b \leq 10^9 \implies \sqrt[3]{b} \leq 10^3\\). Thus, for
any safe point, the points that are inside its umbra also lies in a relatively small square around it. Thus, for each safe point,
we can iterate through all points lying in its umbra and deduct them from our result. To mark the duplicating points, we can
use data structures such as \\(\textit{std::set}\\) in C++.