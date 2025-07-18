---
description: Review your work against the coding guidelines and conventions
---

# Coding Guidelines Review

Read the documentation in @docs/coding-conventions/coding-guidelines.md and revise what you just did. Think hard about where you might have broken the conventions.

Please review your recent work against these key areas:

## Core Conventions to Check:

- **Data Flow**: Did you use Server Components for data loading and Server Actions only for mutations?
- **Service Layer**: Are you calling service functions directly instead of making database calls?
- **TypeScript**: Are you using interfaces over types, proper typing, and Zod validation?
- **File Structure**: Does your code follow the proper import order and organization?
- **Component Architecture**: Are you following the server-first approach with proper component boundaries?
- **Permission Patterns**: If working with API routes, did you implement proper permission checks?
- **Pagination**: Are you using the standard PaginatedRequest/PaginatedResponse pattern?
- **Testing**: Are you following the integration-first testing approach with proper factories?

Identify any violations and suggest specific improvements to align with the documented conventions.
