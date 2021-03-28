# Attributes
#wiki #cs4375

**Attributes** are characteristics of an object. The values of an attributes are assigned via numbers or symbols.

A particular attribute can be mapped to multiple different values, while different attributes can be mapped to the same set of values.

The measurement of an attribute may not necessarily match the properties of the attribute.

## Types of attributes
### Categorical
#### Nominal
- Can represent things like ID numbers, eye color, and zip codes.
- Supported operations: `==`, `!=`

#### Ordinal
- Can represent things like rankings, grades, and height.
- Supported operations: `<=`, `>=`, `<`, `>`, `==`, `!=`

### Numeric
#### Interval
- Can represent things like dates and temperatures
- Supported operations: `+`, `-`, `<=`, `>=`, `<`, `>`, `==`, `!=`

#### Ratio
- Can represent things like temperature in Kelvin, length, time, count
- Supported operations: `*`, `/`, `+`, `-`, `<=`, `>=`, `<`, `>`, `==`, `!=`

## Permissible transformations
### Categorical attributes
#### Nominal
- Acceptable transformation: any one-to-one mapping (e.g. a permutation of values)
- Example: if you map `[red, black, green]` to `[1, 2, 3]`

#### Ordinal
- Acceptable transformation: Any order-preserving change of values [$f(\text{old}) =\text{new}$] where $f$ is a monotonic function
    - **Monotonic function** = a function between ordered sets that preserves or reverses the given order
- Example: if you convert a five-item Likert to a number `[strongly disagree, disagree, neither, agree, strongly agree]` to `[-2, -1 , 0, 1, 2]`

### Numeric attributes
#### Interval
- Acceptable transformation: $\text{new} = a * \text{old}+b$, where $a$ and $b$ are constants
- Example: converting from ºC to ºF

#### Ratio
- Acceptable transformation: $\text{new} = a * \text{old}$, where $a$ is a constant
- Example: if you convert feet to meters

## Attribute domains
The domain of attributes can be defined in two ways:

### Discrete
- Has only a finite set of values
- Often represented as integer variables
- Example: zip codes, counts, set of words in a document

### Continuous
- Has real numbers as values
- Often represented as floating-point variables
- (Limited precision thanks to floats)
- Example: temperature, height, weight
