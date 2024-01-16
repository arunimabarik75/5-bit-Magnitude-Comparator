# 5-bit-Magnitude-Comparator

This readme file provides a detailed design logic explanation for a 5-bit magnitude comparator project implemented using Logisim.

## Design Logic

Let the first binary number be A, represented as A<sub>4</sub>A<sub>3</sub>A<sub>2</sub>A<sub>1</sub>A<sub>0</sub>.
Let the second binary number be B, represented as B<sub>4</sub>B<sub>3</sub>B<sub>2</sub>B<sub>1</sub>B<sub>0</sub>.

Define the following variables:
- x<sub>0</sub> = A<sub>0</sub> ⊕ B<sub>0</sub> = A<sub>0</sub>B<sub>0</sub> + A<sub>0</sub>'B<sub>0</sub>'
- x<sub>1</sub> = A<sub>1</sub> ⊕ B<sub>1</sub> = A<sub>1</sub>B<sub>1</sub> + A<sub>1</sub>'B<sub>1</sub>'
- x<sub>2</sub> = A<sub>2</sub> ⊕ B<sub>2</sub> = A<sub>2</sub>B<sub>2</sub> + A<sub>2</sub>'B<sub>2</sub>'
- x<sub>3</sub> = A<sub>3</sub> ⊕ B<sub>3</sub> = A<sub>3</sub>B<sub>3</sub> + A<sub>3</sub>'B<sub>3</sub>'
- x<sub>4</sub> = A<sub>4</sub> ⊕ B<sub>4</sub> = A<sub>4</sub>B<sub>4</sub> + A<sub>4</sub>'B<sub>4</sub>'

### A = B
For A and B to be equal, the following conditions should hold true:
- A<sub>0</sub> = B<sub>0</sub>, which implies x<sub>0</sub> = 1 (Equation 1)
- A<sub>1</sub> = B<sub>1</sub>, which implies x<sub>1</sub> = 1 (Equation 2)
- A<sub>2</sub> = B<sub>2</sub>, which implies x<sub>2</sub> = 1 (Equation 3)
- A<sub>3</sub> = B<sub>3</sub>, which implies x<sub>3</sub> = 1 (Equation 4)
- A<sub>4</sub> = B<sub>4</sub>, which implies x<sub>4</sub> = 1 (Equation 5)

To satisfy the condition A = B, equations 1, 2, 3, 4 and 5 must all be true:
x<sub>0</sub> x<sub>1</sub> x<sub>2</sub> x<sub>3</sub> x<sub>4</sub> = 1

### A > B
If Ai > Bi, then Ai = 1 and Bi = 0. Hence, Ai Bi' = 1.

For A > B, at least one of the following conditions should hold true:
- A<sub>4</sub> > B<sub>4</sub>, which implies A<sub>4</sub>B<sub>4</sub>' = 1 (Equation 1)
- A<sub>4</sub> = B<sub>4</sub> and A<sub>3</sub> > B<sub>3</sub>, which implies x<sub>4</sub> = 1 and A<sub>3</sub>B<sub>3</sub>' = 1 (Equation 2)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub> and A<sub>2</sub> > B<sub>2</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1 and A<sub>2</sub>B<sub>2</sub>' = 1 (Equation 3)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub>, A<sub>2</sub> = B<sub>2</sub> and A<sub>1</sub> > B<sub>1</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1, x<sub>2</sub> = 1 and A<sub>1</sub>B<sub>1</sub>' = 1 (Equation 4)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub>, A<sub>2</sub> = B<sub>2</sub>, A<sub>1</sub> = B<sub>1</sub> and A<sub>0</sub> > B<sub>0</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1, x<sub>2</sub> = 1, x<sub>1</sub> = 1 and A<sub>0</sub>B<sub>0</sub>' = 1 (Equation 5)

To satisfy the condition A > B, at least one of the equations 1, 2, 3, 4 or 5 must be true:
A<sub>4</sub>B<sub>4</sub>' + x<sub>4</sub>A<sub>3</sub>B<sub>3</sub>' + x<sub>4</sub>x<sub>3</sub>A<sub>2</sub>B<sub>2</sub>' + x<sub>4</sub>x<sub>3</sub>x<sub>2</sub>A<sub>1</sub>B<sub>1</sub>' + x<sub>4</sub>x<sub>3</sub>x<sub>2</sub>x<sub>1</sub>A<sub>0</sub>B<sub>0</sub>' = 1

### A < B
If Ai < Bi, then Ai = 0 and Bi = 1. Hence, Ai'Bi = 1.

For A < B, at least one of the following conditions should hold true:
- A<sub>4</sub> < B<sub>4</sub>, which implies A<sub>4</sub>'B<sub>4</sub> = 1 (Equation 1)
- A<sub>4</sub> = B<sub>4</sub> and A<sub>3</sub> < B<sub>3</sub>, which implies x<sub>4</sub> = 1 and A<sub>3</sub>'B<sub>3</sub> = 1 (Equation 2)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub> and A<sub>2</sub> < B<sub>2</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1 and A<sub>2</sub>'B<sub>2</sub> = 1 (Equation 3)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub>, A<sub>2</sub> = B<sub>2</sub> and A<sub>1</sub> < B<sub>1</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1, x<sub>2</sub> = 1 and A<sub>1</sub>'B<sub>1</sub> = 1 (Equation 4)
- A<sub>4</sub> = B<sub>4</sub>, A<sub>3</sub> = B<sub>3</sub>, A<sub>2</sub> = B<sub>2</sub>, A<sub>1</sub> = B<sub>1</sub> and A<sub>0</sub> < B<sub>0</sub>, which implies x<sub>4</sub> = 1, x<sub>3</sub> = 1, x<sub>2</sub> = 1, x<sub>1</sub> = 1 and A<sub>0</sub>'B<sub>0</sub> = 1 (Equation 5)

To satisfy the condition A < B, at least one of the equations 1, 2, 3, 4 or 5 must be true:
A<sub>4</sub>'B<sub>4</sub> + x<sub>4</sub>A<sub>3</sub>'B<sub>3</sub> + x<sub>4</sub>x<sub>3</sub>A<sub>2</sub>'B<sub>2</sub> + x<sub>4</sub>x<sub>3</sub>x<sub>2</sub>A<sub>1</sub>'B<sub>1</sub> + x<sub>4</sub>x<sub>3</sub>x<sub>2</sub>x<sub>1</sub>A<sub>0</sub>'B<sub>0</sub> = 1

## Conclusion
The design logic covers the conditions for A = B, A > B and A < B, along with the corresponding equations.
