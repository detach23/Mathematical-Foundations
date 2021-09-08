# First-Order-Logic

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

## PA-

- 

## PA

- [PA1] PA ⊢ ∀k∈ℕ ∃m∈ℕ ( k = m·2 ∨ k = m·2+1 ), where "2" denotes "(1+1)".
- [PA2] ∀k ∈ ℕ ( 4 | k·k ∨ 4 | k·k+3 ), where (infix) | : ℕ^2→Bool is defined via ∀x,y∈ℕ ( x | y ⇔ ∃t∈ℕ ( x·t = y ) ).
- [PA3] ∀k∈ℕ ( k > 1 ⇒ ∃p∈ℕ ( p > 1 ∧ p | k ∧ ¬∃q∈ℕ ( 1 < q < p ∧ q | p ) ), where "1 < q < p" is short-hand for "1 < q ∧ q < p".

