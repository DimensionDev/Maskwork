---
Status: Draft

---

# Format: PersonaLocator (v2)

## Introduction

PersonaLocator is a binary blob, to uniquely identify a Persona.

## Data Fields

Field Name      | Required
--------------- | --------
Algorithm       | True
Real Key        | True

## Data Values

### Algorithm

Possible values are defined at Appendix 1 (Normalized Name) in Index page.

### Real Key

Each algorithm has its own binary representation of the public key.

This field has the Base58 representation of the binary blob.

## Examples

```
urn:Maskbook:PersonaLocator:2:secp256k1:fepurTAWwFegSKnk28vE5VFGSwrSsV7P4W9oEHttZEby3
```
