# Optional

> Simple Java8-inspired monadic class to represent optional values

# Installation
```shell
npm install --save data-optional
```

# Usage
```typescript
import Optional from 'data-optional';

const empty = Optional.empty();
const value = Optional.of( 20 );

empty.isPresent(); // false
value.isPresent(); // true
```

You can also convert nullable types into optionals.
```typescript
import Optional from 'data-optional';

const empty = Optional.ofNullable( null );
const value = Optional.ofNullable( 1 );

empty.isPresent(); // false
value.isPresent(); // true
```

There are also a number of computations that can be done functionally with this module.
```typescript
value = Optional.ofNullable( 1 );

value = value.map( n => n * 3 ); // Optional.of( 3 )

value = value.flatMap( n => n % 2 === 0 ? Optional.of( n ) : Optional.empty() ); // Optional.empty()

value.orElse( 0 ); // 0
```