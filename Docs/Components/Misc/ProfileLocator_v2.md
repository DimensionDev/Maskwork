---
Status: WIP

---

# Format: ProfileLocator (v2)

## Introduction

ProfileLocator is designed to provide a universal interface for locating a profile on a social network. A ProfileLocator string may be used to calculate the URL of the permanent link of the profile on its social network.

## Data Fields

Field Name              | Required
----------------------- | --------
Domain Name             | True
Intra-Site Unique Name  | True

## Examples

```
urn:Maskbook:ProfileLocator:2:example.com:username
```

```
urn:Maskbook:ProfileLocator:2:weibo.com:+Z2VTu05LlfQ-
urn:Maskbook:ProfileLocator:2:weibo.com:来去之间
```
