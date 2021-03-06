
# Chapter III. Elements of Signal Detection Theory

### The model for signal detection

![Signal detection model](img/SignalDetectionModel.png){#id .class width=60%}

* Contents:
    * Information source: generates messages $a_n$ with probabilities $p(a_n)$
    * Modulator: transmits a signal $s_n(t)$ for message $a_n$
    * Channel: adds random noise
    * Sampler: takes samples from the signal $s_n(t)$
    * Receiver: **decides** what message $a_n$ has been transmitted

### Example

* A simple case (binary):
    * two messages $a_0$ and $a_1$
    * signals are constants (i.e. 0 for $a_0$, 5 for $a_1$)
    * take just 1 sample
    * decide: compare with a threshold

* General case: many messages, various signals, more samples (or continuous)

### Detection for the binary case

* Receiver guesses between two hypotheses:
    * $H_0$: $a_0$ has been transmitted
    * $H_1$: $a_1$ has been transmitted

* The sample $r = s + n$
    * if more samples, then they are vectors $\overrightarrow{r} = \overrightarrow{s} + \overrightarrow{n}$

* Decision based on regions:
    * if $r$ in region $R_0$, then decide $D_0$: was $a_0$
    * if $r$ in region $R_1$, then decide $D_1$: was $a_1$
    * for single sample, regions are intervals: below/above the threshold
    * for 2 samples: regions are areas in a 2D plane, etc.

* Possible errors:
    * **false alarm**: was $a_0$, but decided $D_1$
    * probability is $P(D_1 \cap a_0)$
    * **miss**: was $a_1$, but decided $D_0$
    * probability is $P(D_0 \cap a_1)$

### Minimum risk (cost) criterion

* How to choose the threshold? We need criteria
    * In general: how to delimit regions $R_i$?

* Minimum risk (cost) criterion: assign costs to decisions, minimize average cost
    * $C_{ij}$ = cost of decision $D_i$ when symbol was $a_j$
    * $C_{00}$ = cost for good $a_0$ detection
    * $C_{10}$ = cost for false alarm
    * $C_{01}$ = cost for miss
    * $C_{11}$ = cost for good $a_1$ detection

*  The risk = the average cost
$$R = C_{00} P(D_0 \cap a_0) + C_{10} P(D_1 \cap a_0) + C_{01} P(D_0 \cap a_1) + C_{11} P(D_1 \cap a_1)$$

* Minimum risk criterion: **minimize the risk R**

### Computations

* Proof on table:
    * Use Bayes rule
    * Notations: $w(r | a_j)$ (*likelihood*)
    * Probabilities: $\int_{R_i} w(r | a_j) dV$

* Conclusion, **decision rule is**
$$\frac{w(r|a_1)}{w(r|a_0)} \gtrless \frac{(C_{10}-C_{00})p(a_0)}{(C_{01}-C_{11})p(a_1)}$$
$$\Lambda(r) \gtrless K$$

* Interpretation: effect of costs, probabilities (move threshold)

* Can also apply logarithm (useful for normal distribution)
$$\ln \Lambda(r) \gtrless \ln K$$

* Example at blackboard: random noise with $N(0, \sigma^2)$, one sample

### Ideal observer criterion

* Minimize the probability of decision error $P_e$
    * definition of $P_e$

* Particular case of minimum risk, with
    * $C_{00} = C_{11} = 0$ (good decisions bear no cost)
    * $C_{10} = C_{01}$ (pay the same in case of bad decisions)

$$\frac{w(r|a_1)}{w(r|a_0)} \gtrless \frac{p(a_0)}{p(a_1)}$$

### Maximum likelihood criterion

* Particular case of above, with equal probability of messages

$$\frac{w(r|a_1)}{w(r|a_0)} \gtrless 1$$
$$\ln \frac{w(r|a_1)}{w(r|a_0)} \gtrless 0$$

* Example at blackboard: random noise with $N(0, \sigma^2)$, one sample
* Example at blackboard: random noise with $N(0, \sigma^2)$, **two** samples
