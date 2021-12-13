# @avenueeco/design-system

A SCSS design system based on Bootstrap, to provide styling and theming to all Avenue Code products

# TODO
1. Set variables to all be `!default` to inherit any product overrides
2. Add editor config files
3. Add linting config files
4. Lint staged

# Installation
1. Install as a npm dependency `npm i @avenueeco/design-system.git`
2. Use within your SCSS
    - Want settings, mixins, extends, with no classes?
        - `@import "~@avenueeco/design-system/src/base";`
    - Want access to Bootstrap's grid classes?
        - No need to import the `required` partial!
        - `@import "~@avenueeco/design-system/src/bridge/grid";`
    - Want to load everything? Please reconsider.
        - `@import "~@avenueeco/design-system/src";`
3. How about just the styles needed to make the page pretty?
    - Its hard to say for sure just what you'll need on a page, so `@avenueeco` provides some utility classes and general stylings
    - `@import "~@avenueeco/design-system/src/page";`

# How do variables get determined?
- All variables should be declared in the `src/_theme.scss` file
- When imported in to a Product, Product variables cascade into Theme Variables
- Theme variables cascade into Bootstrap variables

# Overview
- `src/index` -> Entry file into all component, helper, and utility styles
- `src/page` -> Baseline page style, contains css reset, and utility classes
- `src/fonts` -> Baseline font-family, contains css with font-faces styles.
- `src/theme` -> Baseline theme variables. Product implementation can override.
- `src/bridge/${FILE_NAME}` -> Act as a bridge file to Bootstrap, add pertinent styles
    - Each bridge file loads Avenue Eco Variables, and has access to all Mixins/Functions/Variables
