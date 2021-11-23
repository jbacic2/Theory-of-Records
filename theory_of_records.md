# Theory of Records

## Introduction
The theory of records refers to a method of probabilistic analysis due to [Luc Devroy](https://en.wikipedia.org/wiki/Luc_Devroye). In a sequence of numbers <code>a<sub>1</sub>,a<sub>2</sub>,...,a<sub>n</sub></code>, a value <code>a<sub>i</sub></code> is defined to be a *minimum record* if the value <code>a<sub>i</sub></code> is less than all previous values. The term *record* comes from the idea of best performance. For example, in the recording of winning times of the Boston Marathon, when the winner finishes the race in a time less than all previous runners, a new record has been set. Similarly, <code>a<sub>i</sub></code> is a *maximum record* if it is greater than the value of all previous values. For example, an Olympic discus record is a maximum record as a new record has been set if the distance thrown is greater than all previous throws. In this article, the term “record” will be used to refer to minimum record; however, the analysis with maximum records would give the same respective results. 

The theory of records answers the question:
>  For a sequence of `n` values, what is the [expected](https://en.wikipedia.org/wiki/Expected_value) number of records?
When the sequence comes from a permutation of `{1,...,n}` chosen uniformly at random or where the `n` values are [independent and identically distributed random variables](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables) with a given [probability density function](https://en.wikipedia.org/wiki/Probability_density_function)

The theory of records states that the expected number of records is the <code>n</code><sup>th</sup> [harmonic number](https://en.wikipedia.org/wiki/Harmonic_number), <code>H<sub>n</sub> = sum(1/i) for  i = 1, ..., n</code>. 

## Formal Definition and Analysis 
For a sequence of `n` independent and identically distributed random variables, with a given density <code>a<sub>1</sub>,a<sub>2</sub>,..., a<sub>n</sub></code>. The value <code>a<sub>i</sub></code> is a minimum record if <code>a<sub>i</sub> < a<sub>j</sub></code> for all <code>j = 1,...,i-1</code>. 

### Ranks 
For each `i = 1, …, n`, the *rank* <code>r<sub>i</sub></code> defined to be the value such that <code>a<sub>i</sub></code> is the <code>r<sub>i</sub></code>th smallest value of the set <code>{a<sub>1</sub>,a<sub>2</sub>,..., a<sub>i</sub>}</code>.  

--The global `i = 1, …, n`, the rank <code>r<sub>i</sub></code> is defined to be the value such that <code>a<sub>i</sub></code> is the <code>r<sub>i</sub></code>th smallest value of the set <code>{a<sub>1</sub>,a<sub>2</sub>,..., a<sub>i</sub>}</code>. When using random variables with density functions, the probability that <code>a<sub>i</sub> = a<sub>j</sub></code> is 0.Thus, the  rank sequence, <code>r<sub>1</sub>,..., a<sub>r</sub></code>, is a permutation of `{1, …, n}`. Furthermore, since each <code>a<sub>i</sub></code> is chosen independently from the same distribution, each permutation is equally likely. Thus, the probability that the rank sequence is a given permutation of `{1, …, n}` is `1/n!`.--

The global rank of <code>a<sub>i</sub></code> denoted <code>g<sub>i</sub></code> is the value such that <code>a<sub>i</sub></code> is the <code>g<sub>i</sub></code>th smallest value of the set <code>{a<sub>1</sub>,a<sub>2</sub>,..., a<sub>n</sub>}</code>. When using random variables with density functions, the probability that <code>a<sub>i</sub> = a<sub>j</sub></code> is 0. Thus, the gloabl rank sequence, <code>g<sub>1</sub>,..., g<sub>n</sub></code>, is a permutation of `{1, …, n}`. Furthermore, since each <code>a<sub>i</sub></code> is chosen independently from the same distribution, each permutation is equally likely. Thus, the probability that the gobal rank <code>g<sub>1</sub>,..., g<sub>n</sub></code> sequence is a given permutation of `{1, …, n}` is `1/n!`. 

The rank sequence <code>r<sub>1</sub>, r<sub>2</sub>, ..., r<sub>n</sub></code> uniquly determines the global rank sequence and vice versa. Given the rank seqence, one can construct the global rank sequence 

The value <code>a<sub>i</sub></code> is a record in the sequence <code>a<sub>1</sub>,..., a<sub>n</sub></code> if and only if <code>r<sub>i</sub></code> is a record in the sequence <code>r<sub>1</sub>,..., r<sub>n</sub></code>. Thus counting the number of records in <code>a<sub>1</sub>,..., a<sub>n</sub></code> is equivalent to counting the number of records in <code>r<sub>1</sub>,..., r<sub>n</sub></code>.

### Expected Number of Records
Let the random variable `X` denote the number of records in the sequence <code>a<sub>1</sub>,..., a<sub>n</sub></code> and `E[X]` denote the expected value of `X`. From the previous section, `X` is equal to the number of records of the sequence <code>r<sub>1</sub>,..., r<sub>n</sub></code> where <code>r<sub>i</sub></code> is the rank of <code>a<sub>i</sub></code> for `i = 1, …, n`. 

Define the indicator random variable <code>I<sub>i</sub></code>. To be 1 if <code>a<sub>i</sub></code> is a record and 0 otherwise. Then,
<code>X = sum(I<sub>i</sub>) for  i = 1, ..., n</code>
And thus, <br />
<code>E[X] = E[sum(I<sub>i</sub>)] for  i = 1, ..., n = sum(E[I<sub>i</sub>]) for  i = 1, ..., n</code> by the linearity of expectation. 

Consider <code>E[I<sub>i</sub>]</code>.
<code>E[I<sub>i</sub>] = 0\*Pr(I<sub>i</sub> = 0) + 1\*Pr(I<sub>i</sub> = 1) = Pr(I<sub>i</sub> = 1)</code>. 
Since <code>I<sub>i</sub> = 1</code> if and only if <code>r<sub>i</sub></code> is a record, 
<code>E[I<sub>i</sub>] = Pr(r<sub>i</sub> is a record)</code>. By definition of a record, 
<code>Pr(r<sub>i</sub> is a record) = Pr(r<sub>i</sub> = min(r<sub>1</sub>, …, r<sub>i</sub>))</code>. 
Note that the set <code>{r<sub>1</sub>, …, r<sub>i</sub>}</code> contains `i` unique values and is a uniformly random permutation of these values. Furthermore, each subset of `{1,...,n}` having size `i` has equal probability of being the subset <code>{r<sub>1</sub>, …, r<sub>i</sub>}</code>. Consider the ranks of <code>r<sub>1</sub>, …, r<sub>i</sub></code> and call them <code>l<sub>1</sub>, …, l<sub>i</sub></code> such that <code>r<sub>j</sub></code> is the <code>l<sub>j</sub></code> smallest element of <code>{r<sub>1</sub>, …, r<sub>i</sub>}</code>. Then the sequence <code>l<sub>1</sub>, …, l<sub>i</sub></code> is a uniformy random permutation of `{1,...,n}`. 
<code>Pr(r<sub>i</sub> = min(r<sub>1</sub>, …, r<sub>i</sub>)) = Pr(l<sub>i</sub> = 1)</code>. The value `1` occurs at each location of the sequence with equal probability so <code> Pr(l<sub>i</sub> = 1) = 1/i</code>. Therefore  <code>E[I<sub>i</sub>] = 1/i</code>.

So <code>E[X]= sum(E[I<sub>i</sub>]) for  i = 1, ..., n = sum(1/i) for  i = 1, ..., n = H<sub>n</sub></code> where <code>H<sub>n</sub></code> denotes the `n`th harmonic number. 

## Applications

The theory of records has proven to have many applications in probabilistic analysis. 

