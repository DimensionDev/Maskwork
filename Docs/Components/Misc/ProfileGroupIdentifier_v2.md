# Component: ProfileGroupIdentifier (v2)

## Introduction

ProfileGroupIdentifier is designed to provide a universal interface for locating a post on a social network. A ProfileGroupIdentifier string may be used to calculate the URL of the permanent link of the profile group on its social network.

## Data Fields

Field Name      | Required
--------------- | --------
Type            | True
Level-1 ID      | True
Level-2 ID      | False

## Data Values

### Type

Value   | Must Implement    | Description
------- | ----------------- | -----------
F0      | True              | All friends, defined as the overlapping area between F1 and F2
F1      | True              | All profiles being followed by the profile
F2      | True              | All profiles following the profile
F3      | False             | Union set of F1 and F2
FS      | False             | Specific friends
E1      | False             | All friends of all friends
E2      | False             | All friends of all friends of all friends
RG      | False             | Real group

All extensibility designs around this list must start with "EX".

### Level-1 ID

### Level-2 ID

## Examples

```
urn:Maskbook:ProfileGroupIdentifier:2:facebook.com:F0:example.user
urn:Maskbook:ProfileGroupIdentifier:2:facebook.com:RG:closedgroupid
urn:Maskbook:ProfileGroupIdentifier:2:facebook.com:FS:58571ECA5D953B2BF279AAA44E87542355EE95C5D0911550BE1DD4EB9BEF314B91AB6967F68CE510269960B90AABD1C758AB9C9BDB1CD9EE76CB7D88D45A2292
```
