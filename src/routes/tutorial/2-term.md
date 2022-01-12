<script>
    import { Fraction, Term } from '../../../../mathlify/src/index';
    import { math } from '$lib/math';
    const threeX = math('3x');
    const badExamples = math('0x, \\allowbreak 1\\sin x, \\allowbreak -1\\ln 2', {noLineBreak: false});
    const t1 = new Term(0, 'x');
    const t2 = new Term(1, '\\sin x');
    const t3 = new Term(-1, '\\ln 2');
    const t4 = new Term(new Fraction(1,2), 'y');
    const t5 = new Term(1); // "constant" term with an empty string as the variable
    const goodExamples = math(`
        ${t1}, \\allowbreak
        ${t2}, \\allowbreak
        ${t3}
    `, {noLineBreak: false});
    const oneHalf = new Fraction(1,2);
    const three = new Fraction(3);
    const sum = oneHalf.plus(three);
    const addExample = math(`${oneHalf}+${three}=${sum}`);
</script>

# Term class

## The reason for the Term class

"Mathematical terms" like {@html threeX}
are made up of a "coefficient" and a "variable".

In typesetting terms, non-ideal examples include
{@html badExamples}

The Term class in Mathlify is made up of a
`coeff` (of the Fraction class) and a string representing
the `variable`.

Using the Term class gives {@html goodExamples} instead.

```js
const oneHalf = new Fraction(1,2);
const three = new Fraction(3);
const sum = oneHalf.plus(three);
// code for LaTeX markup
`${oneHalf} + ${three} = ${sum}`;
```

to give the following result:

{@html addExample}

## The constructor

## toString method

## Class methods