# First-Order-Logic

## FOL

For (Q1) to (Q5), S is a type, and P is a property, and Q is a 2-parameter property (i.e. "Q(x,y)" is a statement about "x" and "y").
- (Q1) ¬∀x∈S ( P(x) ) ⇒ ∃x∈S ( ¬P(x) ). 
- (Q2) ¬∃x∈S ( P(x) ) ⇒ ∀x∈S ( ¬P(x) ). 
- (Q3) ∃x∈S ( x∈S ) ⇒ ∃x∈S ( P(x) ⇒ ∀y∈S ( P(y) ) ). 
- (Q4) ∀x,y,z∈S ( x=z ∧ y=z ⇒ x=y ). 
- (Q5) ∀x∈S ( ∀y∈S ( Q(x,y) ⇒ P(x) ) ) iff ∀x∈S ( ∃y∈S ( Q(x,y) ) ⇒ P(x) ).

## PA-

- 

## PA

- [PA1] PA ⊢ ∀k∈ℕ ∃m∈ℕ ( k = m·2 ∨ k = m·2+1 ), where "2" denotes "(1+1)".
- [PA2] ∀k ∈ ℕ ( 4 | k·k ∨ 4 | k·k+3 ), where (infix) | : ℕ^2→Bool is defined via ∀x,y∈ℕ ( x | y ⇔ ∃t∈ℕ ( x·t = y ) ).
- [PA3] ∀k∈ℕ ( k > 1 ⇒ ∃p∈ℕ ( p > 1 ∧ p | k ∧ ¬∃q∈ℕ ( 1 < q < p ∧ q | p ) ), where "1 < q < p" is short-hand for "1 < q ∧ q < p".

