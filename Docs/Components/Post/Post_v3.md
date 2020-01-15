# Component: Post (v3)

## Introduction

Post is a core feature of Maskwork.

## Design Principles

## Preprocessing for Transportation

After constructing this object, it should be serialized as JSON and compressed with GZIP and prefixed by `Base64url.decode('EncryptedPost___')` (namely, "12 77 2B CA 9B 5E 74 FA 2C B7 FF FF") and suffixed by SHA-256 hash, to become a binary payload.

For text-based transportation, Base64url encoding must be used.
