# Module-2: Function Improvements - Arrows and Default Arguments

## 1. Arrow Functions

They have 3 main benefits:
- concise
- implicit return
- doesn't rebind the value of this when it's used inside another function

Arrow functions are always *anonymous* functions.

When we use arrow function it doesn't rebound the value of *this* inside of it.
But it just uses the same *this* from the parent scope, in other words it just inherits *this* from the parent scope.

Rule of thumb
When we want to use the same *this* as it's in the current scope then make use of *Arrow Function*.

---

## 2. Default Function Arguments

We can define default value for the function arguments.

When default values are used in case we skip them in the function call.

In case you need to skip one of the default parameters in between, pass "undefined" for it.

```
    function calculateBill(total, tax = 0.15, tip = 0.05)
    {
        return total + (total * tax) + (total * tip);
    }

    console.log('Billing amount', calculateBill(100));

    console.log('Billing amount', calculateBill(100, 0.12));

    // In case you need to skip one of the default parameters in between...
    console.log('Billing amount', calculateBill(100, undefined, 0.15));
```

---

## 3. When NOT to use an Arrow Function

For the following scenarios make use of regular functions instead of Arrow functions.
- When you really need "this" to refer to the current HTML element.
- Inside Object methods you need "this" to refer to the current Object.
- When you need to add a prototype method.
- When you need arguments object.
