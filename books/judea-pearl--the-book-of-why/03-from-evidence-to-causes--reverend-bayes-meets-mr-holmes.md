## Bayesian Networks
- A [[causal diagram]] is a [[Bayesian network]] where every arrow "signifies a direct causal relation, or at least the possibility of one, in the direction of that arrow." [^1]
- [Bonaparte](https://www.bonaparte-dvi.com/) is a forensic tool that is used to identify victims of disasters using DNA from relatives and Bayesian networks.
- [[Bayesian network]]s are used in everyday applications
	- Speech-recognition software
	- Spam filters
	- Weather forecasting
	- Evaluation of potential oil wells
	- FDA's approval process for medical devices
	- Xbox game skill rankings
	- Belief propagation for cell phone signals
- Named, by Judea Pearl, after [Reverend Thomas Bayes](https://en.wikipedia.org/wiki/Thomas_Bayes) who wrote a paper that was posthumously published by [Richard Price](https://en.wikipedia.org/wiki/Richard_Price)
- Bayes' original question was "how much evidence would it take to convince us that something we consider improbable has actually happened?" [^2]
	- The import of his question held theological importance at that time, but the significance to causality is through the ability to deduce the probability of a cause from an effect.
- Pearl supplies the example of a pool table:
	- [[Forward probability]] is asking: given the length of a pool table, what is the probability of the ball stopping within $x$ feet of the end of the table
	- [[Inverse probability]] is asking: given that the ball stopped $x$ feet from the end of the table, what is the likelihood that the table is a given length?
- [[Forward probability]] is much easier to assess because it moves in the direction cause -> effect
- [[Inverse probability]] works in the opposite direction: given the effect, what is the likelihood of any given cause?

### Bayes' Rule

- Suppose that 2/3 customers in a tea shop order tea
- Suppose also that 1/2 of customers who order tea, also order scones
- This means that 1/3 of customers order both tea and scones
- The starting point for [[03-from-evidence-to-causes--reverend-bayes-meets-mr-holmes#Bayes' Rule]] is to notice that we could have analyzed the data in reverse order
	- We could have observed that (given 12 customers) 5/12 ordered scones, and 4/5 of those customers also ordered tea.
	- With these numbers we can also compute that the proportion of customers who order both tea and scones is 1/3 --> (4/5) * (5/12) === 1/3
- P(T) === probability that a customer orders tea
- P(S) === probability that a customer orders a scone
- P(S | T) === probability that a customer orders a scone given that they order tea
- P(T | S) === probability that a customer orders tea given that they order a scone
	- First calculation could be expressed as --> P(S AND T) = P(S | T) P(T)
	- Second calculation could be expressed as --> P(S AND T) = P(T | S) P(S)
	- Because these are both equal to the same thing, they are equal to each other [[Euclid]] [[Euclidean geometry]]
		- This means that P(S | T) P(T) = P(T | S) P(S)
		- We already now P(T) and P(S), so if we have one of the other quantities, we can solve for the other.
- "We can estimate the conditional probability directly in one direction, for which our judgment is more reliable, and use mathematics to derive the conditional probability in the other direction, for which our judgment is rather hazy." [^3]
- [[03-from-evidence-to-causes--reverend-bayes-meets-mr-holmes#Bayes' Rule]] should be viewed "not just as a convenient definition of the new concept of 'conditional probabilty' but as an empirical claim to faithfully represent the English expression 'given that I know.'" [^4]
	- "It acts, in fact, as a normative rule for updating beliefs in response to evidence." [^5]

[^1]: p.95
[^2]: p.97
[^3]: p.101
[^4]: p.103
[^5]: p.103