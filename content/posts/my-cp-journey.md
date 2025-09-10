+++
title = 'My CP Journey'
date = 2024-09-03T14:27:02+05:30
draft = false
categories = ["work"]
+++

## My Competitive Programming Pilgrimage

<details>
<summary><b>Problem: A. Jellyfish and Undertale</b></summary>

**Explanation of the Problem:**

The problem "A. Jellyfish and Undertale" from TLE Eliminator's CP-31 sheet is a 900-rated problem. Here’s a step-by-step breakdown of how to solve it:

1. **Understand the Problem Statement:** Start by carefully reading the problem. Identify the key requirements and constraints. There are always hints available in the question. It was given to us that the timer will decrease by 1 and each tool can be used **at-most once**.

2. **Approach and Strategy:** My initial approach was to simulate the entire process. But I quickly realized that it is not the most optimal approach for the given time constraints. I had to think mathematically. I quickly realized the core of the entire operation was already given to us in the form of the operation **min(c+xi,a)**. All I had to check was the value of the given integer "a" and compare it with the increasing timer.

3. **Code Walkthrough:** Once the approach clicked to me, it became quite simple for me. At every iteration, all I had to do was check if the current value of the timer is more than the given bug value **a** or not. If more, I had to switch the value of the timer and continue with the same operation. My code is given below:

```cpp
// C++ Code
#include <bits/stdc++.h>
using namespace std;

#define endl '\n'
#define int long long

const int MOD = 1e9 + 7;
const int INF = LLONG_MAX >> 1;

signed main()
{
    ios::sync_with_stdio(false);
    cin.tie(NULL);

    int tc;
    cin >> tc;
    while (tc--)
    {
        int a, b, n;
        cin >> a >> b >> n;
        vector<int> arr(n, 0);
        for (int i = 0; i < n; i++)
        {
            int x;
            cin >> x;
            arr[i] = x;
        }

        int ans = b;
        for (int i = 0; i < n; i++) {
            ans += min(a - 1, arr[i]);
        }
        cout << ans << endl;
    }
}
