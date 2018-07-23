---
id: 289-perfect-forward-secrecy
title: Perfect Forward Secrecy
status: draft
created: 2018-07-23
category: core
lead-contributor: @cammellos
contributors:
    - @yenda
    - @adamb
exit-criteria: no
success-metrics: no
clear-roles: no
future-iteration: no
roles-needed:
    - QA
    - Clojure dev
    - Go dev
    - UX designer
okrs:
    - 
    -
---

## Preamble

    Idea: 289-perfect-forward-secrecy
    Title: Perfect Forward Secrecy
    Status: Draft
    Created: 2018-07-23

## Summary

Pefect Forward Secrecy (PFS) is a must have for a secured messenging application. 
The aim of this swarm is to implement PFS in Status and proceed to some architecture
refactoring to make the communication protocol usable as a third party library.

## Swarm Participants

- Lead Contributor: @cammellos
- Contributor: @yenda
- Contributor: @adamb
- QA:
- UX:

## Product Overview

During Basel Meetup, PFS was defined as one of the key priorities.
`Forward secrecy protects past sessions against future compromises of secret keys or passwords`
This will require some changes and refactoring of the communication protocol.

### User Stories

As a user, I want Status to use PFS, so that my past communications are protected
even if my secret keys are compromised (mitigation of potential information
disclosure).

As a third party developper, I want to be able to use the communication protocol
with minimal setup and boilerplate, so that I can create bots or dapps that uses
the protocol.

### Requirements & Dependencies

> Are there bugs or feature requests in other repositories that are part of this
> Idea?

### Security and Privacy Implications

PFS is a critical functionnality for a secure messenger in order to reduce the
risk of information disclosure. Our implementation should be audited and confirmed
as a correct implementation of Signal Double Ratchet Algorithm
(https://signal.org/docs/specifications/doubleratchet/) and X3DH Key Agreement 
Protocol (https://signal.org/docs/specifications/x3dh/).

## Dates

### Minimum Viable Product

Goal Date: 2018-08-13

Description:
- X3DH and double ratchet implemented on status-go side
- bundle can be exchanged by QR code

### Iteration 1

Goal Date: 2018-08-27

Description:
- sessions keys and messages are stored encrypted on device
- chat primitives are provided as a library

## Success Metrics

Does not apply here

## Exit criteria

- PFS is implemented
- communication protocol is specified with schemas for the messages and RFC
describing it
- we provide a library to use our chat primitives

## Copyright

Copyright and related rights waived
via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
