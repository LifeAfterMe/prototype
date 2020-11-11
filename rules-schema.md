# Rules data schema
Common data model for rules.  May be extended for specific instances.  

## Common

```
id: /* required */
title: {document name} /* required */
issuer: {name of issuing entity}
type: {type of document}  
changes:
   - type: death
     instructions: /* simple example (url) */
  - type: address
    instructions: /* complex example */ instructions */
      - url:
      - phone:
      - mail:
```
