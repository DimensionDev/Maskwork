# Component: SoftwareIndicator (v1)

## Introduction

## Examples

```yaml
$this:
    type: object
    description: AGPL compliance
    properties:
        licenses:
            type: array
            description: Multiple license options
            allOf:
                type: object
                license:
                    type: string
                    description: License code as granted by OSI, or self-claimed common unique name
                licenseUrl:
                    type: string
                    description: URI of license document
            reqiured:
                - license
                - licenseUrl
        source:
            type: string
            description: URI of software source code
    reqiured:
        - licenses
        - source
```
