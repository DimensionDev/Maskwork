---
Status: WIP

---

# Component: PublicKeyDeclaration (v2)

## Introduction

PublicKeyDeclaration is designed to represent the public key of a Persona. It is a binary payload in Base58 format.

All Maskwork-supporting softwares must not demand any additional data to identify a public key.

## Data Fields

Field Name          | Description
------------------- | -----------
Magic Header        | String
Version Indicator   | Number 0~57 (1 Base58 digit)
Algorithm Indicator | Number 0~57 (1 Base58 digit)
Real Key            | Base58 String
Checksum            | 1 Base58 digit

## Data Values

### Magic Header

The Magic Header of this payload is "Key".

### Version Indicator

The version of this payload is "1", the digit which represents 0x0 in Base58 format.

### Algorithm

Possible values are defined at Appendix 1 (Normalized Name) in Index page.

The value of this field is the index of the algorithm in Appendix 1.

For example, if the algorithm is SECP256K1, this field will be "1", the digit which represents 0x0 in Base58 format.

### Real Key

Each algorithm has its own binary representation of the public key.

For example, if the algorithm is SECP256K1, this field will have 33 bytes.

### Checksum

The checksum is calculated by:

- Concat Magic Header, Version Indicator, Algorithm Indicator, and Real Key into one string;
- Get the SHA-256 hash of the string;
- Convert the 256-bit hash blob into a Base58 string; and finally
- Get the last character of the Base58 string.

## Examples

### Field-by-field calculation

Field Name          | Result
------------------- | ------
Magic Header        | Key
Version Indicator   | 1
Algorithm Indicator | 1
Real Key            | fepurTAWwFegSKnk28vE5VFGSwrSsV7P4W9oEHttZEby3
Checksum            | y

### Final Result

```
Key11fepurTAWwFegSKnk28vE5VFGSwrSsV7P4W9oEHttZEby3y
```
