# HTTP Message Strategies Meta Document

## Contents

- [Summary](#1-summary)
- [Why Bother?](#2-why-bother)
- [Scope](#3-scope)
- [Design Decisions](#4-design-decisions)
- [People](#5-people)
- [Votes](#6-votes)
- [Relevant Links](#7-relevant-links)

## 1. Summary

This document describes the reasons behind decisions of the HTTP Message Strategies PSR.

## 2. Why Bother?

The HTTP Request-Response Cycle typically includes the following tasks:

1. The client creates a (plain) request object.
2. The client augments that request object.
3. The client sends the request object to the server.
4. The server augments the request object.
5. The server processes the request by:
  1. creating a (plain) response object
  2. augmenting that response object.
6. The server sends the response object back to the client.
7. The client augments the response object.
8. The client processes the fully augmented response object.

Common contracts for these tasks will allow libraries to be decoupled from
concrete frameworks and vice versa.

## 3. Scope

### 3.1. Goals

* Standardize common HTTP Message strategies to process HTTP Messages defined by [PSR-7](http://www.php-fig.org/psr/psr-7/).
* Standardize contracts based on best practices.

### 3.2. Non-Goals

* Standardize or favor any particular application architecture or assume its presence.

## 4. Design Decisions

## 5. People

### 5.1. Editor(s)

* [Michael Mayer](https://github.com/schnittstabil)

### 5.2. Sponsors

* Vacant (Coordinator)
* Vacant

### 5.3. Contributors

People who contributed in discussions, votes, by reviews or in other ways by alphabetical order:

* TBD

## 6. Votes

* **Entrance Vote:** TBD
* **Acceptance Vote:** TBD

## 7. Relevant Links

* TBD
