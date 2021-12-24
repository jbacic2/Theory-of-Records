# Theory of Records

## Introduction
The theory of records refers to a method of randomized probabilistic analysis. In a sequence of numbers <code>A<sub>1</sub>,A<sub>2</sub>,...,A<sub>n</sub></code>, a value <code>A<sub>i</sub></code> is defined to be a *minimum record* if the value <code>A<sub>i</sub></code> is less than all previous values. The term *record* comes from the idea of best performance. For example, in the recording of winning times of the Boston Marathon, when the winner finishes the race in a time less than all previous runners, a new record has been set. Similarly, <code>A<sub>i</sub></code> is a *maximum record* if it is greater than the value of all previous values. For example, an Olympic discus record is a maximum record as a new record is set if the distance thrown is greater than all previous throws. In this article, the term “record” will be used to refer to minimum record; however, the analysis with maximum records would give the same respective results. 

The theory of records answers the question:
>  For a sequence of `n` values, what is the [expected](https://en.wikipedia.org/wiki/Expected_value) number of records?
Where the sequence comes from a permutation of `{1,...,n}` chosen uniformly at random or where the `n` values are [independent and identically distributed random variables](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables) with a given [probability density function](https://en.wikipedia.org/wiki/Probability_density_function).

The theory of records states that the expected number of records is the <code>n</code><sup>th</sup> [harmonic number](https://en.wikipedia.org/wiki/Harmonic_number), <code>H<sub>n</sub> = sum(1/i) i:1, ..., n</code>. 

## Formal Definition and Analysis 
For a sequence of `n` independent and identically distributed random variables with a given density, <code>A<sub>1</sub>,A<sub>2</sub>,..., A<sub>n</sub></code>. The value <code>A<sub>i</sub></code> is a minimum record if <code>A<sub>i</sub> < A<sub>j</sub></code> for all <code>j = 1,...,i-1</code>. 

### Ranks 
For each `i = 1,..., n`, the *local rank* <code>R<sub>i</sub></code> defined to be the value such that <code>A<sub>i</sub></code> is the <code>R<sub>i</sub></code>th smallest value of the set <code>{A<sub>1</sub>,A<sub>2</sub>,..., A<sub>i</sub>}</code>.  The value <code>A<sub>i</sub></code> is a record in the sequence <code>A<sub>1</sub>,..., A<sub>n</sub></code> if and only if <code>R<sub>i</sub> = 1</code>.

The *global rank* of <code>A<sub>i</sub></code> denoted <code>G<sub>i</sub></code> is the value such that <code>A<sub>i</sub></code> is the <code>G<sub>i</sub></code>th smallest value of the set <code>{A<sub>1</sub>,A<sub>2</sub>,..., A<sub>n</sub>}</code>. When using random variables with density functions, the probability that <code>A<sub>i</sub> = A<sub>j</sub></code> is 0 for `i` different from `j`. Thus, the global rank sequence, <code>G<sub>1</sub>,..., G<sub>n</sub></code>, is a permutation of `{1,..., n}`. Furthermore, since each <code>A<sub>i</sub></code> is chosen independently from the same distribution, each permutation is equally likely. Thus, the probability that the gobal rank sequence is a given permutation of `{1,...,n}` is `1/n!`. 

The local rank sequence <code>R<sub>1</sub>, R<sub>2</sub>, ..., R<sub>n</sub></code> uniquely determines the global rank sequence. Given the local ranks, one can determine the arrangement of <code>A<sub>1</sub>,A<sub>2</sub>,..., A<sub>n</sub></code> in increasing order by starting with an empty sequence and repeatedly adding `i` at position <code>R<sub>i</sub></code> for `i = 1, ..., n`.
The gobal rank <code>G<sub>i</sub></code> is determined by the index of `i` in the ordered sequence. This implies that given a tuple <code>(r<sub>1</sub>, r<sub>2</sub>, ..., r<sub>n</sub>)</code> where <code>1 <= r<sub>i</sub> <= i</code>, <code>Pr(R<sub>1</sub> = r<sub>1</sub>,R<sub>2</sub> = r<sub>2</sub>, ..., R<sub>n</sub>=r<sub>n</sub>)= 1/n!</code>.

By summing over all cases where <code>R<sub>n</sub>=r<sub>n</sub></code>, <code>Pr(R<sub>n</sub> = r<sub>n</sub>) = 1/n</code> for <code>1<= r<sub>n</sub> <= n</code> for all `n = 1, 2, ...`.
  
The previous two equations give:<code>Pr(R<sub>1</sub> = r<sub>1</sub>, R<sub>2</sub> = r<sub>2</sub>, ..., R<sub>n</sub> = r<sub>n</sub>) = Pr(R<sub>1</sub> = r<sub>1</sub>)\*Pr(R<sub>2</sub> = r<sub>2</sub>)\*...\*Pr(R<sub>n</sub> = r<sub>n</sub>)</code> for <code>1 <= r<sub>k</sub> <= n</code> where <code>k = 1, 2, ...</code>, and for <code>n = 1, 2, ...</code>.

Thus <code>R<sub>1</sub>,R<sub>2</sub>, ..., R<sub>n</sub></code> are mutually independent. 

### Expected Number of Records
Let the random variable `X` denote the number of records in the sequence <code>A<sub>1</sub>,..., A<sub>n</sub></code> and `E[X]` denote the expected value of `X`. 

Define the indicator random variable <code>I<sub>i</sub></code>. To be 1 if <code>A<sub>i</sub></code> is a record and 0 otherwise. Then,
<code>X = sum(I<sub>i</sub>) i:1, ..., n</code>.
And thus, <br />
<code>E[X] = E[sum(I<sub>i</sub>) i:1, ..., n]= sum(E[I<sub>i</sub>]) i:1, ..., n</code> by the linearity of expectation. 

Consider <code>E[I<sub>i</sub>]</code>.
<code>E[I<sub>i</sub>] = 0\*Pr(I<sub>i</sub> = 0) + 1\*Pr(I<sub>i</sub> = 1) = Pr(I<sub>i</sub> = 1)</code>. 
Since <code>I<sub>i</sub> = 1</code> if and only if <code>R<sub>i</sub> = 1</code>, 
<code>E[I<sub>i</sub>] = Pr(R<sub>i</sub> = 1) = 1/i</code> from the previous section.
  
So <code>E[X]= sum(E[I<sub>i</sub>]) i:1, ..., n = sum(1/i) i:1, ..., n = H<sub>n</sub></code> where <code>H<sub>n</sub></code> denotes the `n`th harmonic number. 

### Variance 
Consider the indicator random variable <code>I<sub>i</sub></code> as defined in the last section. The value of <code>I<sub>i</sub></code> is determined by the value of <code>R<sub>i</sub></code> for `i = 1, ..., n`. Since <code>R<sub>1</sub>, R<sub>2</sub>, ..., R<sub>n</sub></code> are mutually independent, <code>I<sub>1</sub>, I<sub>2</sub>, ..., I<sub>n</sub></code> are mutually independent. 

For `i=1, ..., n`, <code>I<sub>i</sub></code> is a Bernoulli random variable which takes 1 with proability `p=1/i` and 0 with probaility `1-p=1-1/i`. Thus the variance of <code>I<sub>i</sub></code> is <code>Var(I<sub>i</sub>) = p(1-p) =(1/i)(1-1/i) = 1/i - 1/i<sup>2</sup></code>. Since <code>I<sub>1</sub>, I<sub>2</sub>, ..., I<sub>n</sub></code> are mututally independent, and <code>X = sum(I<sub>i</sub>) i:1,...,n</code>:</br>
<code>Var(X) = Var(sum(I<sub>i</sub>) i:1,...,n) = sum(Var(I<sub>i</sub>)) i:1,...,n >= sum(1/i - 1/i<sup>2</sup>) i:1,...,n = H<sub>n</sub> - sum(1/i<sup>2</sup>) i:1,...,n = H<sub>n</sub> - H<sub>n</sub><sup>(2)</sup></code>. Where <code>H<sub>n</sub><sup>(r)</sup></code> is a generalization of the harmonic number where <code>H<sub>n</sub><sup>(r)</sup> = sum(1/i<sup>r</sup>) i:1,...,n</code>.

Using [Chebyshev's inequality](https://en.wikipedia.org/wiki/Chebyshev%27s_inequality) and the fact that <code>Var(X) <= H<sub>n</sub></code>, `X` can be bounded by <code>(1-a)H<sub>n</sub> <= X <= (1+a)H<sub>n</sub></code> with high probability. Chebyshev's inequality gives:
<code>P(|X-E[X]|>= aE[X]) <= Var(X)/(aE[X])<sup>2</sup> <= H<sub>n</sub>/(a<sup>2</sup> H<sub>n</sub><sup>2</sup>) = 1/(a<sup>2</sup> H<sub>n</sub>)</code> which goes to zero as `n` goes to infinity. Thus with high probability, `|X-E[X]|>= aE[X]` and thus 
<code>(1-a)H<sub>n</sub> <= X <= (1+a)H<sub>n</sub></code>.

This gives that `X/E[X]` converges to 1 since as `n` approaches infinity, for every `a`, <code>Pr(|X/E[X]-1|>a)=0</code>. 

## Applications

The theory of records has proven to have many applications in probabilistic analysis. Some of these include:
- Bounding the hight of random binary search trees
- Bounding the number of points on the convex hull of a set of random points in a sqaure
- Analyzing the quicksort recursive tree

## References
1. Devroye, Luc. "A note on the height of binary search trees." J. ACM 33, 3 (July 1986), p. 489–498, DOI:https://doi.org/10.1145/5925.5930
2. Devroye, Luc. "Applications of the theory of records in the study of random trees." Acta Inf. 26, 1–2 (Oct. 1988), p. 123–130, DOI:https://doi.org/10.1007/BF02915448
3. Glick, Ned. “Breaking Records and Breaking Boards.” The American Mathematical Monthly, vol. 85, no. 1, Mathematical Association of America, 1978, p. 2–26, https://doi.org/10.2307/2978044.
4. Rényi, Alfréd. “Théorie des éléments saillants d'une suite d'observations.” (1962).

