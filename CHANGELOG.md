# [5.0]

- **BREAKING CHANGE** Removed `customPropertyValue` mixin. Just use custom properties natively, and it will be handled by PostCSS in `mwp-cli` (version `8.x` or higher).

Example:
```
@include customPropertyValue(padding-top, var(--responsive-space), $space);
```
becomes
```
padding-top: var(--responsive-space);
```

# [4.2]

- **Change: ** Added `buttonBase()` and `buttonColor()` mixins. These came from [meetup-web-components](https://github.com/meetup/meetup-web-components/), and will be removed from there once the `swarm-sasstools` dependency is updated to require `4.2` or higher

# [4.1]

- **BREAKING CHANGE** Removed [Bourbon](https://www.bourbon.io/) dependency

# [3.1]

- **Refactor** Code and dependency reorganization. All partials in
  `scss/utils/` now explicitly import their dependencies rather than implicitly
  through a base Sass file. This allows consumers to directly import a utility
  partial from `scss/utils` without needing to also import its dependencies.

# [3.0]

- **BREAKING CHANGE** Removed `responsiveVarContext--base()` mixin. CSS custom
  properties are now the preferred method of declaring a viewport-conditional value.

```
// Old method for viewport-conditional $base value
@include responsiveVarContext--base() {
	.padding--left {
		padding-left: $base;
	}
}

// New method for viewport-conditional property values
.padding--left {
    @include responsiveValue(padding-left, var(--responsive-space), $space);
}

// New method without IE11 fallbacks, or when using [style modules](https://meetup.atlassian.net/wiki/spaces/WEG/pages/421659021/Writing+Style+Modules)
.padding--left {
	padding-left: var(--responsive-space);
}
```

# [2.0]

- **Visual Change** Restyled form inputs. Significantly increases whitespace in 
  form inputs. May cause layouts that rely on specific input height to break.

# [1.7]

- **Visual Change** Type style and scaling redesign. No breaking changes.
	- deprecated `%text--display2`, `.text--display2`
	- deprecated `%text--display3`, `.text--display3`
	- deprecated `%text--heavy`, `.text--heavy`

