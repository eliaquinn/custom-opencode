---
name: react-composition-patterns
description:
  React composition patterns that scale. Use when refactoring components with
  boolean prop proliferation, building flexible component libraries, or
  designing reusable APIs. Triggers on tasks involving compound components,
  render props, context providers, or component architecture. Includes React 19
  API changes.
---

# React Composition Patterns

Composition patterns for building flexible, maintainable React components. Avoid
boolean prop proliferation by using compound components, lifting state, and
composing internals.

## When to Apply

- Refactoring components with many boolean props
- Building reusable component libraries
- Designing flexible component APIs
- Reviewing component architecture
- Working with compound components or context providers

## Rule Categories by Priority

| Priority | Category                | Impact | Prefix          |
| -------- | ----------------------- | ------ | --------------- |
| 1        | Component Architecture  | HIGH   | `architecture-` |
| 2        | State Management        | MEDIUM | `state-`        |
| 3        | Implementation Patterns | MEDIUM | `patterns-`     |
| 4        | React 19 APIs           | MEDIUM | `react19-`      |

## Quick Reference

### 1. Component Architecture (HIGH)

- `architecture-avoid-boolean-props` - Avoid boolean props; use composition
- `architecture-compound-components` - Structure components with shared context

### 2. State Management (MEDIUM)

- `state-decouple-implementation` - Provider manages state; UI consumes interface
- `state-context-interface` - Define generic interface with state, actions, meta
- `state-lift-state` - Move state into providers for sibling access

### 3. Implementation Patterns (MEDIUM)

- `patterns-explicit-variants` - Create explicit variant components
- `patterns-children-over-render-props` - Use children for composition

### 4. React 19 APIs (MEDIUM)

> **React 19+ only.** Skip if using React 18 or earlier.

- `react19-no-forwardref` - Use `ref` prop and `use()` instead

## Full Guide

See individual rule files in `rules/` or the main AGENTS.md document.
