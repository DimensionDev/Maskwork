# Maskwork: Index

## Introduction

Maskbook is a utility software for mitigating surveillance from social network corporations.

Maskwork is the protocol for Maskbook applications. The protocol is a collection of selected payloads, which may be classified into several components. Similarly, HTTP has 2 famous payloads, namely, Request and Response; HTTP includes components like MIME Type and Cookie.

## Maintenance

Maskwork is maintained by Maskwork Special Interest Group (MWSIG). MWSIG has its standard workflows.

## Conventions

### Documentation Conventions

- All wording in these documents abide to IETF RFC 2119.

### Technical Conventions

- Primarily, this specification defines several data structures and the rules around their processing. It is transportation-agnostic in that the concepts can be used within the same process, in many various message passing environments. It uses JSON (RFC 4627) as data format.
- All JSON-based payloads should generally follow Wrapper_v1, unless otherwise noted.
- Only ISO 8601 time is used. Other time representation formats are avoided.
- Identifiers should generally abide to Uniform Resource Name (ITEF RFC 2141).
- In actual practice, the format should generally be "urn:Maskbook:${PayloadType}:${Version}:${InternalIdentifier}".
- Any URN string must be a valid UTF-7 string. However, when encoding any part, the not-to-encode list should include only alphanumerical characters, slash, and dot.
- Only Base64url (RFC 4648) is used in this specification; generic Base64 is not allowed.
- The term "Base58" in this specification specifically refers to the variation adopted by Bitcoin.
- Unless otherwise noted, Hex encoding always uses uppercase characters.
- When a non-ASCII domain name is needed, use Punycode (IETF RFC 3492) encoding.

##Terminologies

- **URN Classifier**: The class part of a URN, like "urn:Maskbook:Post:3".

## Components

### List of Components

- Post
- Persona
- Profile
- Contact Management
- Database Backup
- Misakanet

### Component: Post

Payloads:

- Post
- Comment

### Component: Persona

Payloads:

- PersonaAutobiographyCore
- PersonaAutobiographyPublic
- PersonaAutobiographyPrivate

### Component: Database Backup

Payloads:

- DatabaseBackup

### Component: Misakanet

Payloads:

- SisterhoodInvitation
- SisterhoodInvitationResponse
- SisterhoodCertificate
- ...

## Miscellaneous Minor Details

- EcdhEphemeralKeysDict
- PersonaLocator
- PluginIdentifier
- ProfileGroupIdentifier
- ProfileLocator
- SoftwareIndicator
- UserGroupIdentifier (Deprecated)

## Understanding the Mechanisms

## Appendix 1: Normalized Algorithm Names

Index   | Normalized Name | Common Name
------- | --------------- | -----------
0       | secp256k1       | SECP256K1
1       | ed25519         | Ed25519

## Appendix 2: Extra Fields in JSON Schema

These extra fields are used for notation purposes. If the purpose of a field may be replaced by a predefined field in JSON Schema, it should be replaced on an asynchronous basis.

### alias

The alternative name of this field.

Example: `a1`.

### bitLength

The length of the raw binary blob of this field, measuring by bits.

### class

Which class does this field belong to. The content should be a URN component.

Example: `ProfileLocator:2`.

### realType

A chain of conversion, indicating how the original type is represented in the final format. Each part is a function which accepts some payload and returns another payload. The chain will finally create a payload encoded into the form as indicated by `type`.

Example: `[ 'object', 'json.stringify/string', 'gzip.compress/blob', 'aes.encrypt/blob', 'base64url.encode/string' ]`.

### omitIfAny

This data field should be omitted, if any of the following conditions is true.

Example: `{ "this._variant": [ "min" ] }`. If the value of `this._variant` can be found within array `[ "min" ]`, this data field will be omitted.

## Appendix 3: Using Data Field Alias Names

### Overview

The alias names have 2 categories, namely, global and local.

Global alias names should be uppercase Base26 digits starting from "A". Generally, a global alias name should be allocated only if the data field has multiple occurrences across payloads.

Local alias names should be lowercase Base26 digits starting from "a".

### Global Alias Names Registration Table

Alias Name  | Full Field Name       | First Used By
----------- | --------------------- | -------------
`A`         | ...                   | ...

## Appendix 4: Status of Payload Format

A payload format can be:

Status          | Description
--------------- | -----------
WIP             | Still drafting
Effective       | Current standard
Outdated        | Replaced by a later version
