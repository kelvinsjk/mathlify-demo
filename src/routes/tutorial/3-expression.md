<script>
    import { Fraction, Term, Expression } from '../../../../mathlify/src/index';
    import { math } from '$lib/math';
    const badExamples = math('x + -2 y + 0 \\sin x + 3 x');
    const negativeTwoY = new Term(-2, 'y');
    const zeroSinX = new Term(0, '\\sin x');
    const threeX = new Term(3, 'x');
    const example = new Expression('x', negativeTwoY, zeroSinX, threeX);
    const goodExamples = math(`${example}`);
    const oneHalf = new Fraction(1,2);
    const three = new Fraction(3);
    const sum = oneHalf.plus(three);
    const addExample = math(`${oneHalf}+${three}=${sum}`);
</script>

# Expression class

Multiple terms can be combined together (by addition) to form
an "expression".

## The reason for the Expression class

### A first attempt without Mathlify

When working with expressions, we typically convert addition of
negative terms into subtraction, we do not write out zero terms
and we combine like terms.

Failure to do that leads to the following example:

{@html badExamples}

### Using the Expression class

The Expression class handles these situations to give us

{@html goodExamples}

```js
const negativeTwoY = new Term(-2, 'y');
const zeroSinX = new Term(0, '\\sin x');
const threeX = new Term(3, 'x');
const example = new Expression('x', negativeTwoY, zeroSinX, threeX);
// code for LaTeX markup
`${example}`;
```
