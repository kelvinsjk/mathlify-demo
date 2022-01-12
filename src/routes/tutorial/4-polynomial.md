<script>
    import { Fraction, Polynomial } from '../../../../mathlify/src/index';
    import { math } from '$lib/math';
    const threeX2PlusXMinusTwo = new Polynomial([3, 1, -2]);
    const firstExample = math(`${threeX2PlusXMinusTwo}`);
    const ySquareMinusYCubePlusTwoYFive = new Polynomial(
        [1, -1, 0, 2],
        { 
            variableAtom: 'y',
            ascending: true,
            degree: 5
        });
    const secondExample = math(`${ySquareMinusYCubePlusTwoYFive}`);
</script>

# The Polynomial class

Polynomials are a very common type of expression we will work with
and is implemented as its own class with more methods than
the catch-all Expression class.

## The constructor

To create a Polynomial, we supply an array of coefficients 
(the polynomial is in descending order ending at the constant term by default).

```js
const threeX2PlusXMinusTwo = new Polynomial([3, 1, -2]);
// code for LaTeX markup
`${threeX2PlusXMinusTwo}`;
```

{@html firstExample}

Options can be provided to change the `variableAtom` (which defaults to `"x"`),
to change the polynomial to `ascending` order, and to change the `degree` of the
polynomial.

{@html secondExample}

```js
const ySquareMinusYCubePlusTwoYFive = new Polynomial(
    [1, -1, 0, 2],
    { 
        variableAtom: 'y',
        ascending: true,
        degree: 5
    });
// code for LaTeX markup
`${ySquareMinusYCubePlusTwoYFive}`;
```