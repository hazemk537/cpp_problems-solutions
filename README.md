# Problem solving (Arabic)

#### Playlist link: https://www.youtube.com/playlist?list=PLYknlDiw2kSwdDhTSDoX7ZoVEle8nbZdk

## 1- Complexity of algorithms
#### Extra notes:
* The following picture (from a book called Competitive Programming 3 by Steven Halim) shows a rough estimation about the worst complexity of an algorithm that can be used for a problem of a given size.  

![Image](images/TimeComplexity.png)

* An easier way to get a rough estimation of whether an algorithm will pass for a given problem size or not, is to simply substitute with the problem limit in the equation of the upper-bound function of your algorithm.  
For example, if your algorithm is O(N^2), and N (which is the array size for example) in this problem is up to 1000. Then you can substitute N with 1000 in the N^2 equation, which will give you 1000000.  
If the number you get from this substitution is <= 10^8, then "most probably" your solution will not exceed the time limit for most of the problems (which is about 2 seconds).

#### Problems:
1. http://codeforces.com/problemset/problem/677/A
2. http://codeforces.com/problemset/problem/734/A
3. http://codeforces.com/problemset/problem/791/A
4. http://codeforces.com/problemset/problem/231/A
5. http://codeforces.com/problemset/problem/263/A
6. http://codeforces.com/problemset/problem/112/A
7. http://codeforces.com/problemset/problem/59/A
8. http://codeforces.com/problemset/problem/268/A

---

## 2- Frequency array
#### Extra notes:
* The usage of frequency arrays has its limitations. Remember that you need an array whose size is equal to the value of the largest integer in the original array. Which means that you can't use it if the values in the original array can be up to 10^9 for example.  
In most cases, you can use it for values up to 10^7. However, in some websites like Codeforces, you will be given the amount of memory available for your program, which you can use to calculate (roughly) the maximum size for a frequency array that you could create.

* You can use a frequency array to sort an array in O(M) time, where M is the value of the largest integer in the array. Which could be much more efficient than merge sort (which runs in O(nlogn)) in cases where the array size is large but the values inside the array are bounded with a small number.
I'll leave for you to think about how we could implement this function that can sort an array in O(M) using a frequency array.

#### Problems:
###### Basic problems
1. https://app.codility.com/programmers/lessons/3-time_complexity/perm_missing_elem/
2. https://app.codility.com/programmers/lessons/4-counting_elements/perm_check/
3. https://app.codility.com/programmers/lessons/4-counting_elements/missing_integer/
4. http://codeforces.com/problemset/problem/520/A

###### A little bit harder
1. https://app.codility.com/programmers/lessons/4-counting_elements/frog_river_one/
2. https://app.codility.com/programmers/lessons/4-counting_elements/max_counters/
3. http://codeforces.com/problemset/problem/767/A

---

## 3- Prefix sum
#### Extra notes:
* You can use prefix sum for multi-dimensional arrays. Here is a [video](https://www.youtube.com/watch?v=PwDqpOMwg6U) that
demonstrates how this could be done for for 2D arrays.  
You can apply the same concept to 3D arrays, but it will be a little bit tedious.
For higher dimensions, it's more convenient to use dynamic programming with the
inclusion-exclusion (which is beyond the scope of our training) principle to solve this kind of problems.  
It's also worth mentioning that even the simple 1D prefix sum implicitly uses
dynamic programming and the inclusion-exclusion principle.

#### Problems:
1. https://app.codility.com/programmers/lessons/3-time_complexity/tape_equilibrium/
2. https://app.codility.com/programmers/lessons/5-prefix_sums/passing_cars/
3. https://app.codility.com/programmers/lessons/5-prefix_sums/genomic_range_query/  
<details>
  <summary>Need a hint for the third problem?</summary>
   We answered in the video a query the looked like "How many fives are there in a certain range in the array?".  
   You can apply the same thing for the letters 'A', 'C', 'G' and 'T' (e.g. How many 'A's are there?). And of course you can more easily check whether a letter appeared in the range or not.
</details>

###### A little bit harder
1. http://codeforces.com/problemset/problem/368/B

---

# 4- Complexity of algorithms II
#### Problems:
There are now problems for this video (at least for now), so I will add more problems for the next video to compensate.

#### Want to learn more about the analysis of algorithms?
Watch the last three videos in this [playlist](https://www.youtube.com/playlist?list=PLoK2Lr1miEm-5zCzKE8siQezj9rvQlnca)  
This playlist is also an excellent resource if you want to learn about the implementation of data structures.

---

# 5- C++
#### Additional references:
You can learn more about C++ from this [website](http://www.cplusplus.com/doc/tutorial/), which also has a great documentation for the C++ STL (Standard Template Library). Just open up Google and type: cplusplus + the thing that you are searching for.  
e.g. cplusplus vector or cplusplus sort function

#### Problems:
In the last two videos, we haven't really learned a new algorithm or technique, so it's a good point to stop and practice.

###### Basic problems
1. http://codeforces.com/problemset/problem/433/B (Use the C++ STL sort function)
2. http://codeforces.com/problemset/problem/825/A
3. http://codeforces.com/problemset/gymProblem/100814/I
4. http://codeforces.com/problemset/problem/776/A
5. http://codeforces.com/problemset/problem/828/A
6. http://codeforces.com/problemset/problem/820/A
7. http://codeforces.com/problemset/problem/768/A
8. http://codeforces.com/problemset/problem/821/A   

###### A little bit harder
1. http://codeforces.com/problemset/problem/66/B
2. http://codeforces.com/problemset/problem/761/B
3. http://codeforces.com/problemset/problem/828/B
4. http://codeforces.com/problemset/problem/825/B
5. http://codeforces.com/problemset/problem/102/B

---

# 6- Overflow and type casting
#### Problems:
There are now problems for this video.

---

# 7- Partial sum
#### Extra notes:
* Some people use the terms "Prefix sum" and "Partial sum" interchangeably.

* Feel free to skip this note:
The situation we faced in the video is that we wanted to added some constant value x to all the array elements in the range [l,r].  
A harder problem would be to add x to a[l], x+k to a[l+1], x+2k to a[l+2], ... where k and x are given constants.  
Fortunately, there is an efficient solution for this task, which I will not explain here. However, here is my implementation for it if you want to have a look.

```
typedef long long ll;

#define MAX 1000000+9   //Maximum array size
int a[MAX];
ll inst[MAX], perm[MAX];

///a[l] += x, a[l+1] += x+k, a[l+2] += x+2k, ...
void updateRange(int x, int k, int l, int r)
{
    inst[l] += x;
    perm[l+1] += k;
    perm[r+1] -= k;
    inst[r+1] -= x + (ll)(r-l)*k;
}

///Accumulate the values in the range [l, r] inclusive.
void acc(int l, int r)
{
    ll val = 0, inc = 0;
    for(int i = l; i <= r; i++)
    {
        val += inst[i];
        inc += perm[i];
        val += inc;

        a[i] = val;
    }
}
```

#### Problems:
1. http://codeforces.com/problemset/problem/834/B

---

# 8- Modular arithmetic
#### Problems:
1. http://codeforces.com/problemset/problem/834/A
2. https://app.codility.com/programmers/lessons/2-arrays/cyclic_rotation/

#### A little bit harder:
1. http://codeforces.com/problemset/gymProblem/101466/J
<details>
  <summary>Need a hint?</summary>
   Because of the modulo, the resulting array elements never exceed 3 × 10^7.  
   Therefore, sorting the array using a frequency array in O(M) will be more efficient than sorting it using merge sort in O(NlogN). (See the frequency array's section in the notes).
</details>