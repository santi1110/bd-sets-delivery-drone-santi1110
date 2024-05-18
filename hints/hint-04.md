Remember that a `HashSet` not only uses `equals` but also `hashCode` to determine an objects location. This is why 
whenever you override `equals()` you must also override `hashCode()`. They need to be consistent so that 
if `equals` is true for two objects, then `hashCode` returns the same value for each object. If you only override
`equals`, `hashCode` will still be the default implementation in `Object`. We learned this simply returns the memory 
location for an object.
