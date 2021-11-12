Theory of Records

# Introduction
The theory of records refers to a method of probabilistic analysis proposed by Luc Devroy. In a sequence of numbers `a_1,a_2, … a_n`, a value `a_i` is defined to be a *minimum record* if the value `a_i` is less than all previous values. The term *record* comes from the idea of best performance. For example, in the recording of winning times of the Boston Marathon, when the winner finishes the race in a time less than all previous runners, a new record has been set. Similarly, `a_i` is a *maximum record* if it is greater than value of all previous values. For example, an Olympic discus record is a maximum record as a new record has been set if the distance thrown is greater than all previous throws. In this article, the term “record” will be used to refer to minimum record however the analysis with maximum records would give the same respective results. 

The theory of records answers the question: 
>  Given a list of `n` independent and identically distributed random variables (this needs more), what is the expected number of records?

The theory of records states that this is the `n`^th [harmonic number](https://en.wikipedia.org/wiki/Harmonic_number), $H_n=\sum_{i=1}^n \frac{1}{i}$

# Formal Definition and Analysis 
We are given a sequence of `n` independent and identically distributed random variables, `a_1,a_2,..., a_n`. The value `a_i` is a minimum record if `a_i<a_j` for `j` in `{1, …, i-1}`. 

# Applications

The theory of records has proven to have many applications in probabilistic analysis. 
