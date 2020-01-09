# Maskwork: Index

## Introduction

Maskbook is a utility software for mitigating surveillance from social network corporations.

Maskwork is the protocol for Maskbook applications.

## Convention

- All wording in these documents abide to IETF RFC 2119.
- Primarily, this specification defines several data structures and the rules around their processing. It is transportation-agnostic in that the concepts can be used within the same process, in many various message passing environments. It uses JSON (RFC 4627) as data format.
- All JSON-based payloads should generally follow [PKI QAQ 5](https://github.com/neruthes/PKI-QAQ/issues/5), unless otherwise noted.
- Only ISO 8601 time is used. UNIX time is avoided.

## Components

### List of Components

- Post
- Persona
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
