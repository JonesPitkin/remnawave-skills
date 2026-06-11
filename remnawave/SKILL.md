---
name: remnawave
description: Plan, validate, and route Remnawave-related deployment and operations work using official Remnawave resources as the source of truth.
---

# Remnawave Repository Router

Use this skill when the task involves Remnawave but the detailed operational path is not yet modeled in a specialist subskill.

## Current Scope

- identify whether the task is about installation, panel operation, node integration, routing, or security
- collect the exact Remnawave version, deployment mode, and current failure domain
- validate every production action against official Remnawave sources before mutation

## Working Rules

- do not invent panel fields, API behavior, or node semantics
- if the task depends on version-specific behavior, verify the current official docs and repository first
- when detailed local runbooks are missing, produce a source-backed plan instead of speculative commands
