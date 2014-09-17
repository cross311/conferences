# Doing more with LESS for CSS
#### Todd Anglin, Tuesday 12-1

### Why do we need CSS?
- Separate markup and style (SoC)

### Challenges
- Different browser implementations of CSS
- 15 Browser prefixes, but only about 4 matter. -ms, -moz, -o, -webkit

###  LESS for CSS
- LESS is CSS
- Similar to SASS, but used by Bootstrap
- LESS doesn't:
 - Add CSS support to browsers
 - Detect CSS support in browsers
 - Save you from writing bad CSS
 - Add runtime overhead* (Assuming you compile it before deploying to production)
#### Invalid CSS doesn't make it into the CSS file

### Variables
- Reusable values; can only be defined once
- LESS doesn't check for valid values

### Operations
- In-line CSS operations on any number, color or variable
- Can handle px, %, etc
 - Will use the first unit introduced and then ignore extraneous units
 
### Mixins
- Can define global style rules in LESS that will render into appropriate places, e.g.
`
.shadow(@param: 2px 2px 2px #000){
	-webkit-box-shadow: @param;
	box-shadow: @param; }`
- Above demonstrates parameters and default parameter value
- Can also used named parameters
- Can define mixins for your mixins
- Lots of mixin libraries available
- `@import "mixins/helpers" ` for as many libraries as you want

### Guards
- Mixins that match on expressions (when width <= 20px or similar)

### Rules
- Can be nested to create predictale ID selectors based on grouping of elements

### Different ways to use LESS
- Dynamic runtime parsing client-side (using JavaScript LESS parser)
 - Not a good idea for production
- Dynamic parsing server-side
 - Need to make sure it's correct! 
- Best choice: do your parsing at design time or build time.
- Web Essentials for VS2012+ both compile LESS and other useful markup forms.

@toddanglin

lesscssismore.com: LESS to CSS scratchpad