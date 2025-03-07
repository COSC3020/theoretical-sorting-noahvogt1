# Theoretical Sorting
I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

I did not use any outside resources other than what was on the slides.

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

To verify this crazy claim, I would make my own random arbitrary set of arrays of varying
sizes. For example, a list of size 1 and another of size 10 and another of size 100 up to
1,000,000. This would provide me with a relatively good sample space to check whether this
fantastic new sorting algorithm is correct. I could then - ceteris paribus - run the algorithm
over all of the arrays logging the runtime of each. I could then graph these runtimes and observe
the rate at which the runtime grows. The graph of runtimes must be linear to fit the $O(n)$
statement made about the algorithm.

To disprove the possibility of this, we can use the fact that we can only compare two elements
at any given time. By comparing two elements to each other at a time, we can develop a tree of
choices that can track their way down to the different permutations an array. The number of leaves
on this tree is n! for any array of size n, because this represents every permutation of that array.
The max depth/number of choices that would need to be made to reach the deepest leaf node is represented
by $\log_2n!$. By using Stirling's Approximation, we know that $\log_2n!$  is asymptotically equivalent to
$n\logn$. Therefore, the ultimate lower bound to any sorting algorithm must be $n\logn$  disproving
the researcher.
