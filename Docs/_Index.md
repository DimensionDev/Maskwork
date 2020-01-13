# Maskwork: Index

## Introduction

Maskbook is a utility software for mitigating surveillance from social network corporations.

Maskwork is the protocol for Maskbook applications.

## Convention

- All wording in these documents abide to IETF RFC 2119.
- Primarily, this specification defines several data structures and the rules around their processing. It is transportation-agnostic in that the concepts can be used within the same process, in many various message passing environments. It uses JSON (RFC 4627) as data format.
  - All JSON-based payloads should generally follow [PKI QAQ 5](https://github.com/neruthes/PKI-QAQ/issues/5), unless otherwise noted.
- Only ISO 8601 time is used. Other time representation formats are avoided.
- Identifiers should generally abide to Uniform Resource Name (ITEF RFC 2141).
  - In actual practice, the format should generally be "urn:Maskbook:${PayloadType}:${Version}:${InternalIdentifier}"

## Terminologies

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

### Component: Persona

Payloads:

- PersonaAutobiography

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

- ProfileIdentifier Serialization
- UserGroupIdentifier Serialization

## Appendix 1: Normalized Algorithm Names

Index   | Normalized Name | Common Name
------- | --------------- | -------------
0       | secp256k1       | SECP256K1
1       | ed25519         | Ed25519

## Appendix 2: Extra Fields in JSON Schema

### alias

The alternative name of this field.

Example: `a1`.

### class

Which class does this field belong to. The content should be a URN component.

Example: `ProfileLocator:2`.

### realType

A chain of how the original type is represented in the final encoding format. Each part is a function which accepts some payload and returns another payload. The chain will finally create a payload encoded into the form as indicated by `type`.

Example: `object>bson>aes>base64`.

### omit

Whether should this field be omitted when publishing.

Example: `true`.
