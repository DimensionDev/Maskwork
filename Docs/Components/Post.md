# Component: Post

## Introduction

Post is a core feature of Maskwork.

## Design Principles

## Structure

After constructing this JSON, it should be converted to BSON with Base64 encoding without trailing padding characters. The Base64 string should be prefixed by "EncryptedPost___".

## Data Fields

Field           | Type          | Description
--------------- | ------------- | -------------
`postIv`        | String        | 128-bit entropy, Base64 encoded
`ciphertext`    | String        | Variable length, Base64 encoded
``

## Examples
