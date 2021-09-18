# First-Order-Logic

## Introduction

Truth tables are not enough to capture first-order logic (with quantifiers), so we use inference rules instead. Each inference rule is chosen to be sound, meaning that if you start with true statements and use the rule you will deduce only true statements. We say that these rules are truth-preserving. If you choose carefully enough, you can make it so that the rules are not just truth-preserving but also allow you to deduce every (well-formed) statement that is necessarily true (in all situations).

What you are probably looking for (namely a practical way to rigorously check the logical validity of your arguments) is natural deduction. There are many different styles, the most intuitive type being Fitch-style, which mark subcontexts using indentation or some related visual demarcation. The following system uses indentation and follows the intuition most closely in my opinion. 

## Systems

We can axiomatizise ℕ,ℤ,ℚ,ℝ this way and it is non-trivial to actually construct ℤ,ℚ,ℝ in the base system (PA plus Set Theory) and extend the operations on ℕ to them in the manner that satisfies the axiomatizations here.

## FOL

For (Q1) to (Q5), S is a type, and P is a property, and Q is a 2-parameter property (i.e. "Q(x,y)" is a statement about "x" and "y").
- (Q1) ¬∀x∈S ( P(x) ) ⇒ ∃x∈S ( ¬P(x) ). 
- (Q2) ¬∃x∈S ( P(x) ) ⇒ ∀x∈S ( ¬P(x) ). 
- (Q3) ∃x∈S ( x∈S ) ⇒ ∃x∈S ( P(x) ⇒ ∀y∈S ( P(y) ) ). 
- (Q4) ∀x,y,z∈S ( x=z ∧ y=z ⇒ x=y ). 
- (Q5) ∀x∈S ( ∀y∈S ( Q(x,y) ⇒ P(x) ) ) iff ∀x∈S ( ∃y∈S ( Q(x,y) ) ⇒ P(x) ).

For (Q6) to (Q10), S,T,B,G,V are types, and "f : S→T" denotes "f is a 1-input function-symbol whose input must be of type S and whose output is of type T, and "f : S^2→T" denotes "f is a 2-input function-symbol whose inputs are both of type S and whose output is of type T". Note that if the output type is Bool then it denotes a predicate-symbol instead of a function-symbol.
- (Q6) ∀x∈S ( f(f(f(x))) = f(f(x)) ) ∧ ∀x∈S ∃y∈S ( x = f(y) ) ⇒ ∀x∈S ( f(x) = x ), where f : S→S. 
- (Q7) ∀y∈T ( f(g(y)) = y ) ∧ ∀x∈S ∃y∈T ( g(y) = x ) ⇒ ∀x,y∈S ( f(x) = f(y) ⇒ x = y ), where f : S→T and g : T→S. 
- (Q8) ∀x,y,z∈B ( p(x) = p(y) ∧ p(y) = p(z) ⇒ x = y ∨ y = z ∨ z = x ) ⇒ ∀x∈B ∃y,z∈B ∀w∈B ( p(w) = x ⇒ w = y ∨ w = z ), where p : B→B.
- (Q9) ∀x,y,z∈G ( x*(y*z) = (x*y)*z ) ∧ ∀x,y∈G ( x*i(x) = y*i(y) ) ∧ ∀x∈G ( x*(x*i(x)) = x ) ⇒ ∀x,y∈G ( (i(y)*y)*x = x ), where (infix) * : G^2→G and i : G→G. 
- (Q10) ∀x,y∈V ( c(x,y) ⇒ c(y,x) ) ∧ ∀x,y,z∈V ( c(x,y) ∨ c(y,z) ∨ c(z,x) ) ⇒ ∀w∈V ∃x,y,z∈V ( c(x,y) ∧ c(y,z) ∧ c(z,x) ∧ x ≠ y ∧ y ≠ z ∧ z ≠ x ) ∨ ∃v,w,x,y,z∈V ∀t∈V ( t = v ∨ t = w ∨ t = x ∨ t = y ∨ t = z ), where c : V^2→Bool.

## PA− (PA without induction). 

**Non-strict inequality lemmas**:

∀a,b,c∈ℕ ( a ≤ b ⇒ a+c ≤ b+c )

∀a,b,c∈ℕ ( a < b ≤ c ⇒ a < c ) 

∀a,b,c∈ℕ ( a ≤ b < c ⇒ a < c ) 

∀a,b,c∈ℕ ( a ≤ b ≤ c ⇒ a ≤ c ), where "x ≤ y" is short for "x < y ∨ x = y".

Here we use associativity of +,· to drop brackets whenever not needed. Also, "2" means "1+1" and "4" means "1+1+1+1", and you should omit all steps involving just plain algebra; there is no need to give a proof of things like "(k+1)·(k+1) = k·k+k·2+1".

- [PA−1] ∀k,m∈ℕ ( k<m ⇒ k·2+1<m·2 ). 
- [PA−2] ¬∃x,y,z∈ℕ ( 1<x<y<z<4 ). 
- [PA−3] ∀k∈ℕ ¬∃m,n∈ℕ ( 0 < k·k < m·m < n·n < k·k+3k+5 ). 
- [PA−4] PA− ⊢ No natural is both even and odd.

## PA (which includes induction).

[Strong induction] For any property P on ℕ, ∀k∈ℕ ( ∀i∈ℕ ( i<k ⇒ P(i) ) ⇒ P(k) ) ⇒ ∀k∈ℕ ( P(k) ).

[Well-ordering] For any property P on ℕ, ∃k∈ℕ ( P(k) ) ⇒ ∃m∈ℕ ( P(m) ∧ ∀k∈ℕ ( P(k) ⇒ k≥m ) ).

- [PA1] PA ⊢ ∀k∈ℕ ( ∃m∈ℕ ( k = m·2 ) ∨ ∃m∈ℕ ( k = m·2+1 ) ), where "2" denotes "(1+1)". 
- [PA2] ∀k∈ℕ ( 4 | k·k ∨ 4 | k·k+3 ), where (infix) | : ℕ^2→Bool is defined via ∀x,y∈ℕ ( x | y ⇔ ∃t∈ℕ ( x·t = y ) ). 
- (PA3) ∀k∈ℕ ( k > 1 ⇒ ∃p∈ℕ ( p > 1 ∧ p | k ∧ ¬∃q∈ℕ ( 1 < q < p ∧ q | p ) ), where "1 < q < p" is short-hand for "1 < q ∧ q < p". 
- (PA4) ∀k,m∈ℕ ( k·k = m·m·2 ⇒ k = 0 ). 
- (PA5) ∀k,m∈ℕ ( m > 1 ∧ ¬∃d∈ℕ ( d > 1 ∧ d | k ∧ d | m ) ⇒ ∃x,y∈ℕ ( k·x = m·y+1 ) ).

## RA (Real Analysis).

Useful lemmas:
∀ k,m ∈ ℤ ( k < m ⇒ k + 1 ≤ m )

## ST (Set Theory).

**Credits**:

This Natural Deduction system was created by [user21820](https://math.stackexchange.com/users/21820/user21820) from Math.Stackexchange forums; I organized and studied it.
