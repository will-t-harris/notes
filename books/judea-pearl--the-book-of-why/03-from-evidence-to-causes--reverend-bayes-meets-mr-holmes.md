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

### Bayes's Rule

- [[Teahouse example]]
- Suppose that 2/3 customers in a tea shop order tea
- Suppose also that 1/2 of customers who order tea, also order scones
- This means that 1/3 of customers order both tea and scones
- The starting point for [[03-from-evidence-to-causes--reverend-bayes-meets-mr-holmes#Bayes's Rule]] is to notice that we could have analyzed the data in reverse order
	- We could have observed that (given 12 customers) 5/12 ordered scones, and 4/5 of those customers also ordered tea.
	- With these numbers we can also compute that the proportion of customers who order both tea and scones is 1/3 --> (4/5) * (5/12) === 1/3
- $P(T)$ === probability that a customer orders tea
- $P(S)$ === probability that a customer orders a scone
- $P(S | T)$ === probability that a customer orders a scone given that they order tea
- $P(T | S)$ === probability that a customer orders tea given that they order a scone
	- First calculation could be expressed as --> $P(S AND T) = P(S | T) P(T)$
	- Second calculation could be expressed as --> $P(S AND T) = P(T | S) P(S)$
	- Because these are both equal to the same thing, they are equal to each other [[Euclid]] [[Euclidean geometry]]
		- This means that $P(S | T) P(T) = P(T | S) P(S)$
		- We already know $P(T)$ and $P(S)$, so if we have one of the other quantities, we can solve for the other.
- "We can estimate the conditional probability directly in one direction, for which our judgment is more reliable, and use mathematics to derive the conditional probability in the other direction, for which our judgment is rather hazy." [^3]
- [[Bayes's rule]] should be viewed "not just as a convenient definition of the new concept of 'conditional probabilty' but as an empirical claim to faithfully represent the English expression 'given that I know.'" [^4]
	- "It acts, in fact, as a normative rule for updating beliefs in response to evidence." [^5]

#### 2 Objections to [[Bayes's rule]]

- Philosophical Objection
	- This objection stems from the interpretation of probabilities as a degree of belief. Can we really translate the expression "given that I know" into the language of probabilities?
	- Pearl claims that we should view [[Bayes's rule]] as "an empirical claim to faithfully represent the English expression '**given that I know**'"
		- The argument is that the rule asserts "the belief a person attributes to $S$ after discovering $T$ is never lower than the degree of belief that person attributes to $S$ AND $T$ before discovering $T$"
		- It also implies that "the more surprising the evidence $T$&mdash;that is, the smaller $P(T)$ is&mdash;the more convinced one should become of its cause $S$." [^^6]
- Practical Objection
	- The practical objection is the role of subjectivity in the rule.
	- Going back to the example of a billiards table, someone who has never seen one of these tables in their life has no context for whether most tables are 10 feet, 20 feet, or 100 feet long.
	- He illustrates the solution to this practical objection with a long example discussing breast-cancer screening in 40-year-old women. [[Mammogram example]]
	- The thrust of the argument is that the relative risk of a patient having breast-cancer given a positive test is context dependent. 
		- Because the tests aren't perfect, there are bound to be false-positives.
		- Because the likelihood of the average 40-year-old woman having breast cancer is ~ 1 in 700, false positives can lead to more incorrect diagnoses than correct diagnoses
		- **The tiny number of true positives is overwhelmed by the number of false positives**
		- This illustrates the point that $P(disease | test)$ **is not the same for everyone**
	- Pearl's argument is that [[Bayes's rule]] tells us how to update our hypothetical beliefs in the real world.

### From [[Bayes's rule]] to [[Bayesian network]]s

- Between 1950 and the early 1980s, AI had struggled to formalize the process of inferential thinking. 
- During this period the use of [[expert systems]] organized knowledge as collections of specific and general facts, alongside inference rules connecting them. This worked in theory, but offered no way for the system to deal with inference in the face of uncertainty.
- "The computer could not replicate the inferential process of a human expert because the experts themselves were not able to articulate their thinking process within the language provided by the system." [^7]
- Pearl put forward the notion of representing probability as a network of loosely coupled variables passing messages between themselves, rather than huge probability tables.
	- This idea came from [David Rumelhart](https://en.wikipedia.org/wiki/David_Rumelhart)'s work studying how children read.
	- "The key point is that all the neurons are passing information back and forth, from the top down and from the bottom up and from side to side. It's a highly parallel system, and one that is quite different from our self-perception of the brain as a monolithic, centrally controlled system." [^8]
- The idea of [[belief propagation]] comes out of this message-passing structure if the system repeatedly applies these two rules to every node in the network:
	1. If the message goes from parent to child, the child updates its beliefs using conditional probabilities (like in the [[Teahouse example]])
	2. If the message goes from child to parent, the parent updates its beliefs by multiplying them by a likelihood ratio (like in the [[Mammogram example]])

### [[Bayesian network]]s: What Causes Say About Data

- We've already gone over "simple Bayesian networks":
	- Tea -> Scones
	- Disease -> Test
	- Hypothesis -> Evidence
- In contrast to [[causal diagram]]s, a [[Bayesian network]] carries no assumption that the arrow has any causal meaning. It only indicates that we know the [[Forward probability]]. [[Bayes's rule]] tells us how to reverse the procedure, "specifically by multiplying the prior probability by a likelihood ratio." [^9]



[^1]: p.95
[^2]: p.97
[^3]: p.101
[^4]: p.103 
[^5]: p.103
[^6]: p.103
[^7]: p.109
[^8]: p.110
[^9]: p.113