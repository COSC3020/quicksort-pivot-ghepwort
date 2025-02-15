# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Answers

We define a good pivot as one that split the array into peices no larger than $\frac{3n}{4}$. This gives us a probability of $\frac{1}{2}$ that we pick a good pivot if we pick just one element (ie. the first element).

Choosing three pivots, we know there is an ordering of the pivots where they go from least to greatest. The first/least element in this combination has a $\frac{1}{2}$ chance of being a good pivot and an equally likey chance to be a bad pivot. The same logic applies to the third/greatest element in this combination. This now gives us probabilites of $\frac{1}{4}$ of both being good pivots, $\frac{1}{4}$ of both being bad pivots, and $\frac{1}{2}$ of one being good and one being bad.

If both are good pivots then it is garenteed that the medium pivot will give us a good pivot. If both are bad pivots then we have about a $\frac{1}{2}$ chance of getting a good pivot. If one is good and one is bad, then we know the middle pivot will be somewhere between 0 and $\frac{3n}{4}$. This gives us a $\frac{2}{3}$ chance of picking a good pivot.

Now we need to find the combined probability. To get this number we simply multiply and sum the probabilites together to get $(\frac{1}{4} \cdot 1) + (\frac{1}{4} \cdot \frac{1}{2}) + (\frac{1}{2} \cdot \frac{2}{3}) = \frac{1}{4}+\frac{1}{8}+\frac{1}{3} = 70.83$% of happening.

As a $70.83$% chance is larger than $50$% chance, we can conclude that the medium of 3 pivot is often better than choosing a single pivot.

## Sources

I used [CueMath](https://www.cuemath.com/data/dependent-events/) for a little help on probability and the calculations associated.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.