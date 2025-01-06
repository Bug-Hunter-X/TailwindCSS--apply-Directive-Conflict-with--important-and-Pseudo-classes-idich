# TailwindCSS @apply Directive Conflict with !important and Pseudo-classes

This repository demonstrates a bug where Tailwind's `@apply` directive fails to apply hover styles correctly when the base class uses `!important` and the custom directive includes pseudo-class selectors like `&:hover`.

## Bug Description

When a custom Tailwind directive contains a pseudo-class selector (e.g., `&:hover`) and the base class it's applied to has `!important` set on its styles, the `@apply` directive doesn't properly apply the hover styles. The `!important` flag on the base class overrides the styles intended for the hover state.

## Reproduction Steps

1. Clone this repository.
2. Open `bug.css`. Observe the defined `base-class` and `hover-class`.
3. Open `index.html` (or a similar file that uses the CSS).  The hover effect will not work correctly because the `!important` declaration in the base class takes precedence.
4. Open `bugSolution.css` to see how the issue can be resolved.

## Solution

The solution involves carefully managing the usage of `!important` and potentially refactoring your styles to avoid conflicts between the base class and `@apply` directives. The solution demonstrates a way to handle this by ensuring that the order of styles is correct, and the `!important` flag is carefully applied without disrupting the `@apply` behavior. Avoiding `!important` when possible is always the best practice.

## Contributing

Contributions are welcome!