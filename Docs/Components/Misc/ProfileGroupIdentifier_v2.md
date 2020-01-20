---
Status: WIP

---

# Format: ProfileGroupIdentifier (v2)

## Introduction

ProfileGroupIdentifier is designed to provide a universal interface for locating a post on a social network. A ProfileGroupIdentifier string may be used to calculate the URL of the permanent link of the profile group on its social network.

## Data Fields

Field Name      | Required
--------------- | --------
Type            | True
Primary ID      | True
Secondary ID    | False

## Data Values

### Type

Value   | Must Implement    | Description
------- | ----------------- | -----------
F0      | True              | All friends, defined as the overlapping area between F1 and F2
F1      | True              | All profiles being followed by the profile
F2      | True              | All profiles following the profile
F3      | False             | Union set of F1 and F2
FS      | False             | Specific profiles
GR      | False             | Real group

All extensibility designs around this list must start with "EX".

### Primary ID

For Type    | Primary ID Definition
----------- | ---------------------
`F*`        | Intra-site unique name of the profile which is sharing the post
`FS`        | Intra-site unique name of the profile which is sharing the post
`GR`        | Intra-site unique name of the real group

### Secondary ID

For Type    | Secondary ID Definition
----------- | -----------------------
`F*`        | N/A
`FS`        | List of intra-site unique names, joined by "\*"
`GR`        | N/A

## Examples

```
urn:Maskbook:ProfileGroupIdentifier:2:example.com:F0:example.user
urn:Maskbook:ProfileGroupIdentifier:2:example.com:GR:closedgroupid
urn:Maskbook:ProfileGroupIdentifier:2:example.com:FS:user01*user02*user03
```
