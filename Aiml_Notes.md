# Artificial Intelligence & Machine Learning ESE 
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/Sem_3_Notes.git)

# Table of Contents
1. [Previous Years Questions](#previous-year-questions)


## Syllabus
1. AZ Introduction
2. Heuristic Search
3. Hill climbing Search
4. A* algo and AO* algo
5. Min Max Strategy
6. Predicate Logic and Resolutions
7. Planning ( Graph Plan, SAT plan, Hybrid Research)
8. Belief networks
9. Decision tree
10. SVM


## Previous Year Questions

Q1. a.  **Convert the following statements into predicate logic.**
i) **All VJTI students are smart.**
ii) **Every student except George smiles.**
iii) **Anyone who loves everyone loves himself.**
iv) **Someone walks and someone talks.**

Ans. 


i) **All VJTI students are smart.**
Let:
- \( V(x) \): \( x \) is a VJTI student.
- \( S(x) \): \( x \) is smart.

**Predicate Logic:**  
\[
\forall x \, (V(x) \rightarrow S(x))
\]

---

ii) **Every student except George smiles.**
Let:
- \( T(x) \): \( x \) is a student.
- \( G \): George.
- \( Sm(x) \): \( x \) smiles.

**Predicate Logic:**  
\[
\forall x \, (T(x) \land x \neq G \rightarrow Sm(x))
\]

---

 iii) **Anyone who loves everyone loves himself.**
Let:
- \( L(x, y) \): \( x \) loves \( y \).

**Predicate Logic:**  
\[
\forall x \, \left( \left( \forall y \, L(x, y) \right) \rightarrow L(x, x) \right)
\]

---

iv) **Someone walks and someone talks.**
Let:
- \( W(x) \): \( x \) walks.
- \( T(x) \): \( x \) talks.

**Predicate Logic:**  
\[
\exists x \, W(x) \land \exists y \, T(y)
\]  
*(Note: \( x \) and \( y \) can be the same person or different individuals.)*

--- 


Q1. b. **Describe the Hill climbing algorithm with proper example? VVhat are the problems in Hill Climbing?**



--- 

Q1. c. What is Blocks World Problem? Apply the global heuristics and draw a tree to obtain the Goal state from the Initial state for the
following problem.



## Important Topics

