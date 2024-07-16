---
title: Data Structure and Algorithm
slug: data-structure-and-algorithm
date: 2021-12-13
author: Atharva Joshi
read_time: 5
tags: [Algorithms]
order: 1
hero: https://atharvacodes.netlify.app/static/5b6191f2c688751a4f5f97c389e3ba2d/eea4a/dsa.jpg
draft: false
---

In these new series of blogs we will start learning DSA.

# Introduction to Algorithms.

Many new developers have difficulty learning data structures and algorithms. This problem is mainly because data structures and algorithms are more technical than basic HTML/CSS. Before continuing, I think it would be helpful to first understand how DataStructure & Algorithm is useful.

Data structures and algorithms help you understand how your libraries and frameworks work internally. This knowledge will help you to use them more efficiently and correctly. To develop your skills as a developer, you need at least a basic understanding of the algorithm.

Also when you start maintaining larger applications and need to scale a good understanding of datastructures & algorithms will be very crucial to your success. When your application starts servicing thousands of users and speed becomes important a very good understanding of datastructures will help you in scaling your website to meet the demands of users. Knowledge of algorithms will also help you in solving complex business & computer problems in an efficient manner.Your knowledge of data structures and algorithms is sometimes tested in technical interviews.

before starting it will be sencefull to define Algorithm.

# Algorithm

A simple and complete defination of algorithm would be **A set of steps or instruction for completing a task.** thats it, isn't it simple?😎

- Like recipe of making a tea 🍵 is an algorithm.

In CS algorithm specifically means :- A set of steps a program takes to finish a task. Like in python to print **Hello world** an instruction could be given as

```python
print("Hello world")
```

Where print is an instruction.

# 2 components of Algorithm

1. Solution exists for a given problem

2. Part of understanding algorithm is not just knowing that an algorithm exist but understanding when to apply it, this is called **algorithmic thinking**.

   - Looking into the problem at hand and breaking it down to distinct steps. When you have a set of steps you should then be able to identify which algorithm or data structure is best for the task.

Let's suppose we play simple game where I will decide a number and let my 2 friends guess the number that I choose. When they guess a number I will tell them if their guess is too high or low.

**🥇 The winner is one with fewest tries.**

1. Let's start the game🏏 first with Jhon (player 1). I will choose the number between **1 to 10** and Jhon has to guess the number.

Suppose I choosed - **3** and Jhon started playing.

First question which Jhon asked **Does the range include 1 & 10**.To which my answer is **Yes it includes 1 & 10**,

- This is called establishing bounds on problem.

Now moving to next step. Jhon starts guessing the number :-

- 1 - Too low<br>
- 2 - Too low<br>
- 3 - Correct<br>

Playing same game with Ana (player 2), with all codition as in previous case.

Now Ana starts guessing :-

- 5 - Too high<br>
- 4 - Too high<br>
- 3 - Correct<br>

**It's a tie** both Jhon and Ana guessed the number in 3 tries. Let's play again, this time I choose **10**.

Again starting with Jhon :-

- 1 - Too low<br>
- 2 - Too low<br>
- 3 - Too low<br>
- 4 - Too low<br>
- 5 - Too low<br>
- 6 - Too low<br>
- 7 - Too low<br>
- 8 - Too low<br>
- 9 - Too low<br>
- 10 - Correct<br>

Now Ana's turn:-

- 5 - Too low<br>
- 8 - Too low<br>
- 9 - Too low<br>
- 10 - Correct<br>

# Observing both players approch.

When the answer was '3' both Jhon and Ana took the same number of turns this is important.
When the number was larger but not that much larger (in this case 10) we start to see that Ana's strategy did better, Ana took 4 tries while Jhon took 10 tries.

**Let's play the game for one more time for a range between 1 & 100 including 1 & 100**

This time I choose **5**.

Starting the game with Jhon again:-

- 1 - Too low<br>
- 2 - Too low<br>
- 3 - Too low<br>
- 4 - Too low<br>
- 5 - Correct<br>

Now Ana's turn:-

- 50 - Too high<br>
- 25 - Too high<br>
- 13 - Too high<br>
- 7 - Too high<br>
- 4 - Too low<br>
- 6 - Too high<br>
- 5 - Correct<br>

This time Jhon took 5 tries where as Ana took 7 tries.

🤯 Jhon's approach is called **Linear Search** or **Sequential search** or **Simple Search**. While Ana's approach is called **Binary Search**.

# Some characterstics of algorithm

1. Algorithm should have a clearly defined problem statement, input and output.

2. The steps in the algorithm need to be in very specific order.

3. The steps also need to be distinct.

4. The algorithm should produce a result.

5. The algorithm should complete in a finite amount of time.

<br>
<img src="/src/images/posts/dsa-img/algo.png" alt=dsa>
<br>

Next part coming soon! Till then Code hard try learning basics of python.

<br><br><br>
