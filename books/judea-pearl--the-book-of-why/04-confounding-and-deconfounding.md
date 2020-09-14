# Confounding and Deconfounding: or, Slaying the Lurking Variable

Pearl offers the story of Daniel from Genesis as an example of a [[controlled experiment]].

- King Aspenaz asks a question about causation: Will a vegetarian diet cause my servants to lose weight?
- To understand the causal effect of the diet, he compares what happens to Daniel on the vegetarian diet with what happens to others who do not follow the same.
- The experiment must compare common groups, not just single people.
- The experiment must be prospective, the groups being chosen in advance.
- The one key thing that isn't taken into account is the effect of [[confounding bias]].

> Occurs when a variable influences both who is selected for the treatment and the outcome of the experiment. [^1]

The term confounding originally meant "mixing," indicating that with confounding the causal effects are mixed in some way. The job of the statistician is to determine which variables are true confounders and to remove their influence from the results.

There is a balance to be struck here, as the tendency of most statisticians has been to control for more than they must.

> Statisticians have been immensely confused about what variables should and should not be controlled for, so the default practice has been to control for everything one can measure. [^2]

> Confounding is a causal concept&mdash;it belongs on rung two of the [[Ladder of Causation]] [^3]

It seems that one of the main points that Pearl is making in this chapter is that the hesitance of researchers to make causal claims is overstated. If we can properly adjust for [[confounding bias]], we have a better view of the causal situation and we should be able to make claims about it. If we truly believe that we've eliminated all the important [[confounder]]s, we should also believe in the value of the experiment's results.

[^1]: p.137
[^2]: p.139
[^3]: p.140