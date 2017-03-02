---
title: "Homework 4"
author: "Amil Khan"
date: "3 March 2017"
output: 
  pdf_document: 
    highlight: tango
header-includes: \usepackage{amsthm}
---

# Problem 1

Let $\{X_t \ ; \ t \in \mathbb{N}\}$ be a homogeneous Markov chain, we are going to study
the random variable defined as $T = \inf \{t \in \mathbb{N}; \ X_t = y \}$ which represents the number of
time steps needed to reach a specific state.


Suppose that there are 5 songs on your professor's jogging playlist. He sets the shuffle
mode which plays songs uniformly at random, sampling with replacement (i.e. repeats
are possible). At each time step, a song is played. Let $X_t$ be the number of unique songs
that have been heard after the $t^{th}$ song has been played.


```python
import numpy as np
import scipy as sy
```

## Part a.)

Explain why $\{X_t \ ; \ t \in \mathbb{N}\}$ forms a stationary discrete time Markov chain.



## Part b.)

Simulate on sample path of $\{X_t \ ; \ t \in \mathbb{N}\}$. Print the path and the number of time steps it took for the five songs to be heard.


```python
X = [0]
played_song = set()
# Total number of songs on Professor's playlist
num_songs = 5
while True:
    song = np.random.choice( range(num_songs) )
    played_song.add(song)
    num_played = len(played_song)
    X.append(num_played)
    if num_played == num_songs:
        break
print(X)
```

    [0, 1, 2, 3, 3, 3, 4, 4, 4, 4, 5]


## Part c.)

Simulate 10000 trajectories of the process and store them in a list.


```python
length_num_played = []
n = 10000 
for k in range(0,n):
    X = [0] 
    played_song = set() 
    num_songs = 5 
    while True:
        song = np.random.choice( range(num_songs) )
        played_song.add( song )
        num_played = len( played_song )
        X.append( num_played )
        if num_played == num_songs:
            break
    length_num_played += [len(X)-1]
```

## Part d.)

## Part e.)

## Part f.)






