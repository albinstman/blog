---
layout: post
title:  "Tensors In Quantum Mechanics"
date:   2024-04-07 00:39:55 +0200
categories: jekyll update
---

# This blog post explores why tensors are so prevalent in quantum mechanics

Before we can begin and talk about **tensors** in Quantum Mechanics we need to start with a refresher on how we can represent the state of a particle.  

We know from Quantum Mechanics that an electron or any other particle can be represented as a state vector $ \overrightarrow{\boldsymbol{v}} $. We also know that this state vector can be written as a linear combination (or superposition) of all possible configurations where the coefficients are the the probabilities of that particular configuration occurring

$$ \overrightarrow{\boldsymbol{v}} = P(\overrightarrow{\boldsymbol{v_1}})\overrightarrow{\boldsymbol{v_1}} + P(\overrightarrow{\boldsymbol{v_2}})\overrightarrow{\boldsymbol{v_2}} + P(\overrightarrow{\boldsymbol{v_3}})\overrightarrow{\boldsymbol{v_3}} + \ ...$$

This is all the details we need to begin our talk about **tensors**!

---

Let’s describe a hypothetical particle that has both <em>spin</em> and <em>color</em>. The possible configurations for the <em>spin</em> state is ↑ or ↓ and 🔴 or 🔵 for <em>color</em>. 
And we know the probabilities for the particles <em>spin</em> and <em>color</em> as

$$P(↑) = 0.5 \quad  P(↓) = 0.5 \quad P(🔴) = 0.7 \quad P(🔵) = 0.3 $$

We now have two different states vectors to describe this particle

$$ \overrightarrow{\boldsymbol{v}} = P(↑)\ *↑ + \ P(↓)\ *↓ = 0.5\ *↑ + \ 0.5\ *↓ $$

$$ \overrightarrow{\boldsymbol{w}} = P(🔴)\ *🔴 + \ P(🔵)\ *🔵 =0.7\ *🔴 + \ 0.3\ *🔵 $$

Instead of dealing with the two vectors $\overrightarrow{\boldsymbol{v}}$ and $\overrightarrow{\boldsymbol{w}}$ our goal is to package these vectors into a new vector that can fully represent our particle.

Let $T$ be our <em>packaging function</em> that takes our two different state vectors $\overrightarrow{\boldsymbol{v}}$ and $\overrightarrow{\boldsymbol{w}}$ into a new single state vector $\overrightarrow{\boldsymbol{z}} = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$

$$T(\overrightarrow{\boldsymbol{v}}, \overrightarrow{\boldsymbol{w}}) = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$$

Where $⊗$ is just a symbol for the combination of $\overrightarrow{\boldsymbol{v}}$ and $\overrightarrow{\boldsymbol{w}}$.

There is already some basic things we know about this new vector $\overrightarrow{\boldsymbol{z}} = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$

1. All possible configurations of $\overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$ is a combination of configurations of $\overrightarrow{\boldsymbol{v}}$ and $\overrightarrow{\boldsymbol{w}}$.
This is a complicated way of saying our particle can only end up as one of these four configurations

$$↑, \ 🔴 \quad  ↓, \ 🔴  \quad ↑, \ 🔵 \quad ↓, \ 🔵 $$

2. Probabilities of the new configurations is a multiplication of the configurations involved.
For example the probability that the particle has <em>spin</em> ↑ and <em>color</em> 🔴 is

$$P(↑, 🔴) = P(↑) * P(🔴) = 0.5 * 0.7 = 0.35 $$

By using the same formula we get the other three probabilities

$$P(↓, 🔴) = 0.35 \quad P(↑, 🔵) = 0.15 \quad P(↓, 🔵) = 0.15 $$

We are now ready to write the new state vector $\overrightarrow{\boldsymbol{z}} = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$ as a linear combination of its possible configurations and corresponding probabilities

$$\overrightarrow{\boldsymbol{z}} = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}} = P(↑,🔴)*(↑, \ 🔴) + P(↓,🔴)*(↓, \ 🔴) + P(↑,🔵)*(↑, \ 🔵) + P(↓,🔵)*(↓, \ 🔵) = \\ P(↑)*P(🔴)*(↑, \ 🔴) + P(↓)*P(🔴)*(↓, \ 🔴) + P(↑)*P(🔵)*(↑, \ 🔵) + P(↓)*P(🔵)*(↓, \ 🔵) = \\ 0.35*(↑, \ 🔴) + 0.35*(↓, \ 🔴) + 0.15*(↑, \ 🔵) + 0.15*(↓, \ 🔵)$$

Now we turn back to our packaging function $T$. If we expand $\overrightarrow{\boldsymbol{v}},\ \overrightarrow{\boldsymbol{w}}$ and $\overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$ into their linear combination we get the following

$$ T(P(↑)\ *↑ + \ P(↓)\ *↓,\ P(🔴)\ *🔴 + \ P(🔵)\ *🔵) = \\ P(↑)*P(🔴)*(↑, \ 🔴) + P(↓)*P(🔴)*(↓, \ 🔴) + P(↑)*P(🔵)*(↑, \ 🔵) + P(↓)*P(🔵)*(↓, \ 🔵) = \\ 0.35*(↑, \ 🔴) + 0.35*(↓, \ 🔴) + 0.15*(↑, \ 🔵) + 0.15*(↓, \ 🔵) $$

We recognize that this is equal to moving sums and probabilities outside the function for both arguments.

This <em>packaging function T</em> where the sums and probabilities behave this way is called <em>bilinear</em>. 

We can now turn to the definition of a **tensor**. A **tensor** is an element of the product of two vector spaces with an associated <em>bilinear</em> function. It should now be clear that this new state vector $\overrightarrow{\boldsymbol{z}} = \overrightarrow{\boldsymbol{v}} ⊗ \overrightarrow{\boldsymbol{w}}$ is a **tensor**. Since it is a product of vectors with an associated <em>bilinear</em> function.

Just by combining two independent states, <em>spin</em> and <em>color</em> of a particle, in a way that probabilities are calculated properly, we arrive that the new state must be a **tensor** product of the other two states. 

How exciting!