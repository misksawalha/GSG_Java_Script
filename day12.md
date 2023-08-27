
## Equality: 
- Double equal : allows coercion (types different) , so we use with null or undefined
- Triple equal : disallows coercion (types same) , so we use it when types are the same
- The case for preferring Double equal : is about comparisons with known type(s), optionally
where conversions are helpful

### TypeScript : 
#### Benefits: 
-   Catch type-related mistakes
- Communicate type intent
-  Provide IDE feedback
 
#### Caveats: 
- Inferencing is best-guess, not a guarantee
- Annotations are optional
- Any part of the application that isn't typed introduces uncertainty


### Tasks :