

#### [Dynamics Semantics](http://dynsem.github.io/): Veltman's Epistemic Modals



##### Introduction

The first few pages of @VeltmanDefaults provides a simple test semantics for 'might' that has become hugely influential in the literature on epistemic modals and indicative conditionals.  Here I present, first, the actual semantics Veltman gives, and, second, a more standard variant of it assumed in the literature.  I then comment on some features of the semantics, including its relationship to treatment of epistemic modality in @YalcinEpistemic.  

##### Preliminaries

Assume a set of _worlds_, $W$.  Contexts (sample $c$) are just sets of worlds.  Atomic formulae $a \ldots z$ are assigned sets of worlds by the interpretation function $I : A \to \mathcal{P}(W)$.

#### Veltman's dynamic semantics 

where $\phi$ is atomic:

$c[\phi] = c \cap I(\phi)$

for any $\phi$ and $\psi$:

$c[\lnot \phi] = c \backslash c[\phi]$

$c[\phi \land \psi ] = c[\phi] \cap c[\psi]$

$c[\phi \lor \psi ] = c[\phi] \cup c[\psi]$

$c[\Diamond \phi] = \{ w \in c : c[\phi] \neq \emptyset \}$

(_or, equivalently:_

$c[\Diamond \phi] =  \begin{cases}
c \text{,  if } c[\phi] \neq \emptyset \\
\emptyset \text{,  otherwise} \end{cases}$)

##### Standard modifications

Veltman's semantics does not explicitly define 'must' as the dual of 'might' and it provides a non-standard dynamic semantic entry for conjunction: merely intersecting the result of the two updates rather than having consecutive updates. Standardly, we would view conjunction and epistemic necessity modals as follows:

$c[\phi \land \psi ] = (c[\phi])c[\psi]$

$c[\Box \phi] = c [\lnot \Diamond \lnot \phi] = \{ w \in c : c[\phi] = c \}$

(_or, equivalently:_

$c[\Box \phi] =  \begin{cases}
c \text{,  if } c[\phi] \neq c \\
\emptyset \text{,  otherwise} \end{cases}$)


##### Consistency and coherence

For a sequence of updates $\phi_1 \ldots \phi_n$ we can define whether it is _consistent_ or _coherent_ as follows:

$\phi_1 \ldots \phi_n$ is _consistent_ if there exists a context $c$, such that $c[\phi_1] \ldots [\phi_n] \neq \emptyset$.

$\phi_1 \ldots \phi_n$ is _coherent_ if there exists a context $c$, such that $c[\phi_1] \ldots [\phi_n] = c$.

We can extend these definition to single formulas in the usual way.  With dynamic conjunction the consistency and/or coherence of a sequence is equivalent to the consistency and/or coherence of the conjunction of its members in sequential order.

#### Belief

What is it to believe a CCP in this semantic system?  If a belief state, $s$ determines a set of worlds $b_s$ consistent with beliefs at $s$ then $b_s$ counts as believing a CCP $\phi$ iff $b_s[\phi] = b_s$ (i.e. $b_s$ is a fixed point of $\phi$).  We can extend this to belief in a sequence of updates in the expected way: $b_s$ counts as believing the sequence  $\phi_1 \ldots \phi_n$ iff $b_s[\phi_1] \ldots [\phi_n] = b_s$.  Note that belief in a sequence is only possible if the sequence is coherent.

We can extend the language to include belief attributions as follows:

$c[\text{John believes } \phi] = \{ w \in c : j_w [\phi] = j_w \}$ 

where $j_w$ are all the worlds consistent with John's beliefs at $w$.

We now can see that $c[\text{John believes }\Diamond a ] = \{ w \in c : j_w \cap a \neq \emptyset \}$ = those worlds in $c$ where John has a belief world in which $a$ is true.  See @YalcinEpistemic for arguments that this is a good result.

##### Epistemic contradictions

Note that the sequence $a, \Diamond \lnot a$ is neither consistent nor coherent, while the sequence $\Diamond \lnot a, a$ is consistent but not coherent.

Veltman and others have made much of the order sensitivity of consistency.  However, it is not clear to me what important empirical implications this has.

@YalcinEpistemic noted that _epistemic contradictions_ of the form $p \land \Diamond \lnot p$ or conversely $\Diamond \lnot p \land p$ seem not only unassertable (as to be expected as they are Moorean paradoxical), but also do not embed well in various environments such as under 'suppose':

(@one) ? Suppose it's raining and it might not be raining.

Compare:

(@) Suppose it's raining and I don't know it's raining.

This data would seem to be straightforwardly explained by Veltman's semantics for epistemic modals: as the  $\lnot p \land \Diamond p$ is not a coherent and hence it cannot be the content of a suppositional state.  (Assuming 'suppose $\phi$' is an instruction to enter a suppositional state with content $\phi$.) 




##### Test semantics indicative conditionals

@GilliesEpistemic gives a test semantics for indicative conditionals modelled on Veltman's semantics for epistemic modals.  The basic ideas is that an indicative conditional is a test restricted to the context after the antecedent has been applied.

$c[\phi \to \psi] = \{w \in c : c[\phi][\psi] = c[\phi]\}$

_or, equivalently_

$c[\phi \to \psi] =  \begin{cases}
c \text{,  if } c[\phi][\psi] = c[\phi] \\
\emptyset \text{,  otherwise} \end{cases}$

##### Understanding tests

The use of tests in dynamic semantics leads to pressing questions about how the conversational effect of dynamic sematnic values is to be understood.  Surely it is not the case that conversations where tests fail actually go to the absurd (empty) context.  Rather we must supplement our dynamic semantics with a kind of pragmatic story about how tests are used by speakers to convey information or otherwise communicate.


##### Odd Embeddings


As noted in @KlinedinstRothschildEC there are some embeddings of Veltman's epistemic modals that have unexpected semantic values.  For example, consider the negation of an epistemic contradiction $\lnot (\Diamond p \land \lnot p)$.  This does not act as a tautology as you might expect.  It is a fixed point of both any context in which $p$ holds throughout the context and any context in which $p$ fails throughout the context.  


##### Comparison with @YalcinEpistemic

See this [note](vy.html) for a comparison of Yalcin and Veltman, using the version of Yalcin in @KlinedinstRothschildConnectives




#### Bibliography

