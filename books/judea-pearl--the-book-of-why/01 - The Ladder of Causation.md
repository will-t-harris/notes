# The Ladder of Causation

- First encountered the ladder in reading Genesis for "the hundredth time"[^1].
- God asked Adam and Eve *what* they had done, they both answered with *why*.
	- G: "Have you eaten from the tree which I forbade you?"
		- Adam: "The woman you gave me for a companion, she gave me fruit from the tree and I ate".
	- G: "What is this you have done?"
		- Eve: "The serpent deceived me, and I ate".
- He asked for the facts, and they gave him explanations.
- More importantly, **both somehow were convinced that naming causes would paint their actions in a different light**.
- He believes these nuances carry three "profound implications":
	1. Early in our evolution, we realized that the world consists not only of dry facts, but rather an intricate web of cause-effect relationships.
	2. Causal explanations make up the bulk of our knowledge, and should be the cornerstone of machine intelligence.
	3. Our transition from "processors of data" to "makers of explanations" wasn't gradual, it required an external push (the forbidden fruit of Eden). He extrapolates that **no machine can derive explanations raw data without an external push**.
- Somehow we as a species developed a "causal imagination" that allows us to imagine nonexistent things. He, along with Yuval Harari, think that this was the key to everything.
- Returning to the story of Genesis, it is impossible to claim that Eve caused you to eat the fruit if you are unable to posit a counterfactual. It necessitates the ability to imagine a world in which she did not hand you the fruit.
- This is essentially the establishment of a mental model as the arena within which imagination takes place. 
	- He gives a hunting example: humans are able to consider the effect of different factors on the success of a hunt. More hunters, better weather, size of the animal, differing terrain, etc. This is a layer of abstraction on top of raw experience that is unique to humans, it seems.

 ## The Three Levels of Causation

### Seeing / Association

- Involves detection of regularities in our environment.
- Many animals share in this level.
- We say that one event is associated with another if observing one changes the likelihood of observing the other.
- **Activity**: Seeing, observing
- **Questions**: 
	- What if I see...? 
	- How are the variables related?
	- How would seeing X change my belief in Y?
- **Examples**: 
	- What does a symptom tell me about a disease? 
	- What does a survey tell us about the election results?

### Doing / Intervention
- "Involves predicting the effect(s) of deliberate alterations of the environment and choosing among these alterations to produce a desired outcome." [^2]
- Few other animals share in this level.
- Use of tools, as long as it is intentional use, can be taken as a sign of reaching this level.
- **Activity**: Doing, intervening
- **Questions**: 
	- What if I do...? 
	- How? 
	- What would Y be if I do X?
	- How can I make Y happen?
- **Examples**:
	- If I take aspirin, will my headache be cured?
	- What if we ban cigarettes?

### Imagining / Counterfactuals

- Possessing a theory of the tool telling us why it works and what to do when it doesn't.
- This level, he argues, is what prepared us for revolutions in agriculture and science and led to the drastic change in our species' impact on the planet.
- **Activity**:
	- Imagining
	- Retrospection
	- Understanding
- **Questions**:
	- What if I had done...?
	- Why?
	- Was it X that caused Y?
	- What if X had not occurred?
	- What if I had acted differently?
- **Examples**:
	- Was it the aspirin that stopped my headache?
	- Would Kennedy be alive is Oswald had not killed him?
	- What if I had not smoked for the previous 2 years?

- Modern machine learning programs operate almost entirely on the first level, as they did thirty years ago.
	- "They are driven by a stream of observations to which they attempt to fit a function" [^3] Raw data drives this fitting process.
	- "If, for example, the programmers of a driverless car want it to react differently to new situations, they have to add those new reactions explicitly. The machine will not figure out for itself that a pedestrian with a bottle of whiskey in hand is likely to respond differently to a honking horn. This lack of flexibility and adaptability is inevitable in any system that works at the first level of the Ladder of Causation." [^4]

- The second level is characterized by intervention. '"What will happen to floss sales if we double the price of toothpaste?"'
	- This involves not only seeing, but changing what is.
	- Questions about intervention cannot be answered with passively collected data, no matter how much of it we have.
	- "A direct way to predict the result of an intervention is to experiment with it under carefully controlled conditions." [^5]
		- e.g. Facebook performing UI experiments with small subsets of their customer base. They can hold all other variables equal except for the UI changes and observe the difference in behavior.
	- If we have a sufficiently strong and accurate **causal model**, we can use observational data (rung-one) to answer interventional (rung-two) questions.
		- The causal model is required for machine learning to answer questions about interventions, because the causal model breaks the rules of the environment the machine was trained in. It won't be able to break out to a level of intervention-type thinking without a causal model to bring it up another level.

- The third level consists of counterfactuals. Why questions.
	- To answer these questions we must in effect go back in time, change history, and ask "What would have happened if I had not done X?"
	- "This ability most distinguishes human from animal intelligence, as well as from model-blind versions of AI and machine learning." [^6]
	- Science is already in the habit of making useful claims about would-haves, things that have not happened.
		- **The laws of physics can be interpreted as counterfactual assertions:**
			- Had the weight on a spring doubled, the length of the spring would have doubled as well.
			- Assertions such as this one are backed by a huge amount of experimental (rung-two) knowledge, derived from observing a large number of springs in many laboratories over many many different occasions.
			- Once we have "derived a law" in physics, all possible different worlds with any weight $x$ and any length $L_{x}$ are treated as objectively knowable and simultaneously active, even though only one scenario exists at any given point in time.
	- Yuval Harari believes the depiction of imaginary creatures is a manifestation of a new ability in man. He calls this the **Cognitive Revolution**, and traces the nascence of this ability to the [Lion Man sculpture](https://en.wikipedia.org/wiki/Lion-man) found in Stedel Cave in SW Germany from roughly 40,000 years ago.
		- He points to this as **the earliest example of a creature that is pure imagination.**
		- The argument is that this sculpture is a precursor of every philosophical theory, scientific discovery, and technological innovation. "Every one of these had to take shape in someone's imagination before it was realized in the physical world." [^7]

## The Mini-Turing Test

- Turing's "imitation game" (put forward in 1950) posits that a computer could be called a "thinking machine" if an ordinary human communicating via text could not tell whether they were communicating with a human or a computer.
	- Turing also proposed a strategy for passing the imitation game: "Instead of trying to produce a program to simulate the adult mind, why not rather try to produce one which simulates the child's? Presumably the child brain is something like a notebook as one buys it from the stationer's. Rather little mechanism, and lots of blank sheets." [^8]
- The [Loebner Prize](https://en.wikipedia.org/wiki/Loebner_Prize) competition offers $100,000 to any program that can fool all four of its judges. Over the last 25 years, no program has even fooled half of the judges.
- **The key component of this "childlike intelligence" is a mastery of causation**.
- Pearl's "mini-Turing" test asks the question: "How can machines (and people) represent causal knowledge in a way that would enable them to access the necessary information swiftly, answer questions correctly, and do it with ease, as a three-year-old child can?" [^9]
	- The process is to first take a simple story, encode it on a machine somehow, and then test to see if the machine is able to answer causal questions that a human could answer.
	- "mini" for two reasons
		1. Confined to causal reasoning, excluding other realms of human knowledge such as vision and natural language.
		2. The story can be encoded in any "convenient representation." The machine is not burdened with acquiring the story from personal experience.
	- The representation is really important, and needs to come first, because without representation we wouldn't know how to store information for future use.
		- Paradigm in AI and the study of cognition: "Representation first, acquisition second."
	- Causal diagrams not only can communicate knowledge easily, but these models pass the mini-Turing test.

### Firing Squad Example

- Scenario is that a prisoner is about to be executed by firing squad. A certain chain of events *must* occur for this to happen.
1. Court orders the execution (CO)
2. Order goes to a captain (C)
3. Captain signals the soldiers (A, B) to fire
4. Assume that (A, B) never miss, they only fire on command, and if either one shoots the prisoner dies (D)

#### Association Diagram

```mermaid
graph TD
CO-->C
C-->A
C-->B
A-->D
B-->D
```

- Each of the unknowns (CO, C, A, B, D) is a boolean value: D === true means the prisoner is dead; D === false means the prisoner is alive
- Using this graph we can start answering causal questions:
	- **Association**: If the prisoner is dead, does that mean the court order was given?
		- We can trace up the graph and, using standard logic, conclude that the soldiers wouldn't have fired without their captain's command, which had to come from a court order
	- **Intervention**: What is A decides to fire on his own initiative? Will the prisoner be dead or alive?
		- If just using rules of logic, this question is meaningless because it goes against the "rules" defined in the original arrangement. **Computers are not good at breaking rules**.
		- We need to "teach" the computer the difference between **observing** an event and **making an event happen**
			- To the computer: "Whenever you make an event happen, remove all arrows that point to that event and continue the analysis by ordinary logic, as if the arrows had never been there."
			- "Making an event happen means that you remove it from all other influences and subject it to one influence&mdash;that which enforces its happening."" [^10]

#### Intervention Diagram

```mermaid
graph TD;
classDef FixFont font-size:11px;
CO --> C;
C --> B;
A[A==True]:::FixFont --> D;
B --> D;
```

	[^1]: p.24
	[^2]: p.27
	[^3]: p.30
	[^4]: p.31
	[^5]: p.32
	[^6]: p.33
	[^7]: p.35
	[^8]: p.37
	[^9]: p.37
	[^10]: p.41