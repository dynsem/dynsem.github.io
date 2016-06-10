Yalcin and Veltman  {#comparison .unnumbered}
---

This appendix explores the relationship between @YalcinEpistemic andl
Veltman’s [-@VeltmanDefaults] semantics for epistemic modals. A
modification of Yalcin’s semantics from @KlinedinstRothschildConnectives
is used as well as the standard modification of Veltman’s semantics
discussed.

#### Basic assumptions {#basic-assumptions .unnumbered}


We assume again a language $\mathcal{L}$ syntax of propositional logic
with modal operators for both semantics and a standard set of worlds. We
write ${[\hspace{-.02in}[{a}]\hspace{-.02in}]}$ for the worlds in which
the atomic formula $a$ is true (what we wrote as $I(a)$ earlier). For
the dynamic system we give a semantics that assigns to sentence an
update on an arbitrary sentence $c$ (the update of $\phi$ on $c$ is
written $c[\phi]$. For the static semantics we define a denotation
function ${[\hspace{-.02in}[{\cdot}]\hspace{-.02in}]}$ that gives
relative to a world $w$ and a context $s$ (again a set of worlds) a
truth-value (i.e.
${[\hspace{-.02in}[{\cdot}]\hspace{-.02in}]}: \mathcal L  \times W \times \mathcal P (W) \to  \{0,1\}$).
We then prove that both systems induce the same ‘updates’.

#### Modified Veltman semantics {#veltmans-semantics .unnumbered}


$c[a] = c \cap {[\hspace{-.02in}[{a}]\hspace{-.02in}]}$

$c[\lnot \phi] = c \backslash c[\phi]$

$c[\phi \land \psi] = (c[\phi])[\psi]$

$c[\phi \lor \psi] = c[\phi] \cup (c[\lnot \phi])[\psi]$

$c[\Box \phi] = c$, if $c[\phi] = c$, otherwise $\emptyset$

$c[\Diamond \phi] = c[\lnot \Box \lnot  \phi]$

#### Modified Yalcin Semantics {#static-semantics .unnumbered}

${[\hspace{-.02in}[{A}]\hspace{-.02in}]}^{w, s}$ is true iff $w$ is in
${[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}$.

${[\hspace{-.02in}[{\lnot \phi }]\hspace{-.02in}]}^{w,s}$ is true iff
${[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,s}$ is false.

${[\hspace{-.02in}[{\phi \land \psi}]\hspace{-.02in}]}^{w,s}$ is true
iff ${[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,s}$ is true and
${[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}^{w,s{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}}$
is true.

${[\hspace{-.02in}[{\phi \lor \psi}]\hspace{-.02in}]}$ is true iff
${[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,s}$ is true or
${[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}^{w,s{[\hspace{-.02in}[{\lnot \phi}]\hspace{-.02in}]}}$
is true.

${[\hspace{-.02in}[{\Box \phi}]\hspace{-.02in}]}^{w,s}$ is true iff
$\forall w' \in s$
${[\hspace{-.02in}[{\Box \phi}]\hspace{-.02in}]}^{w',s}$ is true.

${[\hspace{-.02in}[{\Diamond \phi}]\hspace{-.02in}]}^{w,s}$ is true
iff ${[\hspace{-.02in}[{\Box \lnot \phi}]\hspace{-.02in}]}$ is false.

where $c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}$, the update of $c$ by
$\phi$, it is defined as follows:

$c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]} = \{w \in c: {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,c} \textrm{ is true}\}$

#### Equivalence {#equivalence .unnumbered}


The following limited equivalence statement may be made between the two
semantics:

> __For any sentence $\phi$ any context $c$, and any world $w$,
> $w \in c[\phi]$ iff
> $w \in c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}$.__

Proof is by induction on formula complexity.

Base case

:   if $\phi$ is simple then the question is just whether $w$ is in
    its denotations for both semantics, so the equivalence is trivial.

Induction Step

:   Suppose for sentences $\phi$ and $\psi$, for any $c$ and
    $w \in c$, that $w \in c[\phi]$ iff
    $w \in c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}$. 

    By case:

    Negation

    :   $w$ in $c[\lnot\phi]\\ \textrm{iff } 
        w \in c \backslash c[\phi]\\  \textrm{iff } 
         w \not \in c[\phi]  \\  \textrm{iff } 
        w \not \in c {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]} \text{ (by induction hypothesis)} \\ \textrm{iff } 
        {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,c}\textrm{ is false}\\ \textrm{iff } 
        {[\hspace{-.02in}[{\lnot \phi}]\hspace{-.02in}]}^{w, c}\textrm{ is true}\\ \textrm{iff } 
        w \in c{[\hspace{-.02in}[{\lnot \phi}]\hspace{-.02in}]}$

    Conjunction

    :   $w \in c[\phi \land \psi] \\ \textrm{iff } 
        w \in (c[\phi])[\psi] \\ \textrm{iff } 
        w \in c[\phi] \text{ and } w\in (c[\phi])[\psi] \text{ (given monotonicity of dynamic updates)}\\ \textrm{iff } 
        w \in  c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]} \textrm{ and } w\in  (c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}){[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}  \text{ (by induction hypothesis)}\\ \textrm{iff } 
        {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,c}\textrm{ is true}\textrm{ and } {[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}^{w,c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}}\textrm{ is true} \\ \textrm{iff } 
        c{[\hspace{-.02in}[{\phi \land \psi}]\hspace{-.02in}]}^{w,c}\textrm{ is true}\\ \textrm{iff } 
        w \in (c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}){[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}$

    Disjunction

    :   Very similar to conjunction, so shortened here:\
        $w \in c[\phi \lor\psi]  \\ \textrm{iff } 
        w \in c[\phi]\textrm{ or }w \in (c[\lnot \phi])[\psi] \\ \textrm{iff } 
        {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,c}\textrm{ is true or } {[\hspace{-.02in}[{\psi}]\hspace{-.02in}]}^{w,c{[\hspace{-.02in}[{\lnot \phi}]\hspace{-.02in}]}}\textrm{ is true} \\ \textrm{iff } 
        w \in c{[\hspace{-.02in}[{\phi \lor \psi}]\hspace{-.02in}]}$

    Necessity Modal

    :   $w \in c[\Box \phi]\\ \textrm{iff } 
        c[\phi] = c \\  \textrm{iff } 
        \forall w \in c, w \in c[\phi] \\ \textrm{iff } 
        \forall w \in c, w \in c{[\hspace{-.02in}[{\phi}]\hspace{-.02in}]} \\ \textrm{iff } 
        \forall w \in c, {[\hspace{-.02in}[{\phi}]\hspace{-.02in}]}^{w,c}\textrm{ is true}\\ \textrm{iff } 
        {[\hspace{-.02in}[{\Box \phi}]\hspace{-.02in}]}^{w,c}\textrm{ is true}\\ \textrm{iff } 
        w \in c {[\hspace{-.02in}[{\Box \phi}]\hspace{-.02in}]}$

    Possibility Modal

    :   Follows from previous proofs since defined in terms of necessity
        modal and negation.


