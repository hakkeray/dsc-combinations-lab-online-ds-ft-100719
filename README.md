
# Combinations - Lab

## Introduction

Now, let's dive into combinations. In the previous lab, you saw how the order was important when using permutations. Cracking a code is one example, but what if the order doesn't matter, for example, when an engaged couple wants to pick 3 wedding cakes from a list of 15? You'll need to use another technique here, and this is where combinations come in handy!

## Objectives

You will be able to: 

* Decide whether or not permutations and combinations are required for a given problem
* Use Python to calculate combinations and permutations


## Let's get started

From the previous lab, you remember that we created a factorial function.

Now, let's use this factorial function to create a function `combination` as well as `permutation`, both holding 2 arguments n and k.


```python
def factorial(n):
    prod = 1
    while n >= 1:
        prod = prod * n
        n = n - 1
    return prod
```


```python
def permutation(n,k):
    return factorial(n)/(factorial(n-k))
```


```python
def combination(n,k):
    return factorial(n)/(factorial(n-k) * factorial(k))
```

Great! We can use these functions in the following exercises.

## Permutations or Combinations?

Flatiron School is holding a mini mathematics contest and there are 9 people in the last round. 

#### a. Imagine flatiron school is giving out bronze, silver, and gold medal respectively. How many possible ways are there to create this top three?


```python
medal_top_3 = permutation(9,3)
medal_top_3 # 504.0
```




    504.0



#### b. Imagine Flatiron school granting the first three contestants a massive fruit basket. How many ways of selecting three people are there in this case?


```python
scholarship_top_3 = combination(9,3)
scholarship_top_3 # 84.0
```




    84.0



## Some More Practice using Combinations

Imagine you have 6 different consonants and 4 different vowels written on pieces of paper in a bag. You'll draw 5 letters out of the bag. 

#### a. What is the probability that you draw exactly 2 consonants and 3 vowels when drawing 5 letters?

Write the code for getting total number of ways of drawing 2 out of 6 and 3 out of 4 below


```python
draw_cons = combination(6,2)
draw_vow = combination(4,3)
```

The total number of ways to draw 5 letters out of 10 letters.


```python
sample = combination(10,5)
```

The probability of drawing 2 consonants and 3 vowels when drawing 5 letters:


```python
(draw_cons * draw_vow) / sample # 0.23809523809523808
```




    0.23809523809523808



#### b. Out of 6 consonants and 4 vowels, how many words with 2 consonants and 3 vowels can be formed?

You can reuse a part of the previous exercise. Which part? print the result below.


```python
draw_cons = combination(6,2)
draw_vow = combination(4,3)
```

Now we need to take into account that order is important.


```python
order_5_letters = factorial(5)
```

The total number of words with 2 consonants and 3 vowels then equals:


```python
total_words = draw_cons * draw_vow * order_5_letters
print("In total,",  total_words, "words with 2 consonants and 3 vowels can be formed from our existing letter pool.")
# In total, 7200.0 words with 2 consonants and 3 vowels can be formed from our existing letter pool.
```

    In total, 7200.0 words with 2 consonants and 3 vowels can be formed from our existing letter pool.


## Combinations: Creating Soccer Teams
We're holding a mini soccer tournament and 16 people are participating. We'd like to form 4 teams of 4. How many ways are there to do this?


```python
# 63063000.0
team_one = combination(16,4)  
team_two = combination(12,4)
team_three = combination(8,4)
team_four = combination(4,4)
all_combined = team_one*team_two*team_three*team_four


print(team_one, team_two, team_three, team_four)
all_combined
```

    1820.0 495.0 70.0 1.0





    63063000.0



## Summary

In this lab, you got some practice with combinations, and deciding whether or not combinations and permutations are required for a problem. Congrats! Combinations and permutations are the cornerstones of combinatorics, and you now know how to use Python to compute them in various settings.
