---
title: Relative vs Absolute Test Coverage
description: Avoiding a false sense of quality
date: 2024-12-13
tags: ['Process Improvement']
---

When discussing test coverage, it’s important to distinguish between two concepts: **absolute coverage** and **relative coverage**. Misunderstanding or failing to communicate the distinction can lead to a false sense of quality and misplaced confidence in testing outcomes.

## Absolute Coverage

Absolute coverage measures testing against every possible scenario that could occur in the system. This includes every input, every configuration, every edge case, and every combination of conditions.

This is often impractical, if not impossible to work against.

## Relative Coverage

Relative coverage measures testing against a subset of scenarios that are known and considered relevant. This is typically what teams refer to when they report on coverage, such as the percentage of critical paths or features that are tested.

This is often what we default to when conveying coverage.

## Danger of Miscommunication

One common pitfall is reporting relative coverage without making it clear that it is not absolute. For example, a tester might say, “My smoke pack has 100% coverage and all tests pass.” At face value, this sounds reassuring, but without clarification, stakeholders might interpret this as absolute coverage and assume the system is entirely fault-free.

In reality, our tests are likely based against a subset of known features, behaviours, or paths and this is what the coverage is measured against; we should aim to provide this additional context whenever reporting on test outcomes regardless of how obvious we, as testers, may think it is.
