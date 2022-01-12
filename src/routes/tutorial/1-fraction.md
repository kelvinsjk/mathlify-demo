<script>
    import { Fraction } from '../../../../mathlify/src/index';
    import { math } from '$lib/math';
    const oneThird = math('\\frac{1}{3}');
    const latex = math('\\LaTeX');
    const badExamples = math('\\frac{2}{4}, \\allowbreak \\frac{-1}{-3}, \\allowbreak \\frac{1}{-5}, \\allowbreak \\frac{0}{6}, \\allowbreak \\frac{7}{1}', {noLineBreak: false});
    const f1 = new Fraction(2,4);
    const f2 = new Fraction(-1,-3);
    const f3 = new Fraction(1,-5);
    const f4 = new Fraction(0, 6);
    const f5 = new Fraction(7, 1);
    const goodExamples = math(`
        ${f1}, \\allowbreak
        ${f2}, \\allowbreak
        ${f3}, \\allowbreak
        ${f4}, \\allowbreak
        ${f5}, \\allowbreak
    `, {noLineBreak: false});
    const oneHalf = new Fraction(1,2);
    const three = new Fraction(3);
    const sum = oneHalf.plus(three);
    const addExample = math(`${oneHalf}+${three}=${sum}`);
</script>

# Fraction class

## The reason for the Fraction class

### Professional typesetting

The fraction "one third" is sometimes expressed
as an ASCII string `1/3`
or the floating point 
representation `0.333`. Neither representation is ideal.

Using {@html latex} allows us to express it as {@html oneThird}.

Trying to implement fractions programatically with a naive approach could
lead to the following:

{@html badExamples}

The Fraction class in Mathlify does automatic simplification of fractions, giving us the following instead:

{@html goodExamples}

### Arithmetic operations and other methods

Arithmetic operations are implemented as class methods, allowing for the following code

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