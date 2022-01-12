<script>
    import { Fraction, SquareRoot } from '../../../../mathlify/src/index';
    import { math } from '$lib/math';
    const twoRootTwo = new SquareRoot(8);
    const three = new SquareRoot(9);
    const goodExamples = math(`${twoRootTwo}, ${three}`);
</script>

# The SquareRoot class

{@html goodExamples}


## The constructor

To create a Polynomial, we supply an array of coefficients 
(the polynomial is in descending order ending at the constant term by default).

```js
const threeX2PlusXMinusTwo = new Polynomial([3, 1, -2]);
// code for LaTeX markup
```
