# Component: PersonaLocator (v2)

## Introduction

PersonaLocator is a binary blob, to uniquely identify a Persona.

## Data Fields

Field Name      | Required
--------------- | --------
Algorithm       | True
Actual Payload  | True

## Data Values

### Algorithm

Possible values are defined at Appendix 1 (Normalized Name) in Index page.

### Actual Payload

Each algorithm has its own binary representation of the public key.

## Examples

```
urn:Maskbook:PersonaLocator:2:secp256k1:AWFceyl2VOyvyeaqkTodUI1XulcXQkRV
```
