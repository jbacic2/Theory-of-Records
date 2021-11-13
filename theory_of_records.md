Theory of Records

# Introduction
The theory of records refers to a method of probabilistic analysis due to [Luc Devroy](https://en.wikipedia.org/wiki/Luc_Devroye). In a sequence of numbers <code>a<sub>1</sub>,a<sub>2</sub>,...,a<sub>n</sub></code>, a value <code>a<sub>i</sub></code> is defined to be a *minimum record* if the value <code>a<sub>i</sub></code> is less than all previous values. The term *record* comes from the idea of best performance. For example, in the recording of winning times of the Boston Marathon, when the winner finishes the race in a time less than all previous runners, a new record has been set. Similarly, <code>a<sub>i</sub></code> is a *maximum record* if it is greater than value of all previous values. For example, an Olympic discus record is a maximum record as a new record has been set if the distance thrown is greater than all previous throws. In this article, the term “record” will be used to refer to minimum record however the analysis with maximum records would give the same respective results. 

The theory of records answers the question: 
>  Given a list of `n` independent and identically distributed random variables (this needs more), what is the expected number of records?

The theory of records states that this is the <code>n</code><sup>th</sup> [harmonic number](https://en.wikipedia.org/wiki/Harmonic_number), <code>H<sub>n</sub> = sum(1/i), i = 1, ..., n</code>

# Formal Definition and Analysis 
We are given a sequence of `n` independent and identically distributed random variables, <code>a<sub>1</sub>,a<sub>2</sub>,..., a<sub>n</sub></code>. The value <code>a<sub>i</sub></code> is a minimum record if <code>a<sub>i</sub> < a<sub>j</sub></code> for <code>j</code> in <code>{1,...,i-1}</code>. 

# Applications

The theory of records has proven to have many applications in probabilistic analysis. 
