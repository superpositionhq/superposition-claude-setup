---
description: Update existing documentation to reflect recent changes
---

# Update Documentation

Update existing documentation to reflect the recent changes, improvements, or new features we've implemented.

## Your Task:

1. Identify which documentation files need to be updated based on recent changes
2. Review existing documentation for outdated information
3. Update relevant sections with new information
4. Ensure consistency across all documentation
5. Add new sections if needed for new features or changes

## Documentation to Check:

- **README files**: Update setup instructions, usage examples, feature lists
- **Tech Design Docs**: Docs created in @docs

## Update Guidelines:

- Maintain consistent formatting and style
- Keep documentation concise and focused - avoid unnecessary filler words
- Update version numbers and dates where applicable
- **DO NOT write actual code in documentation** - only use:
  - Pseudo-code for illustrating concepts
  - Code references to actual implementation files
  - Brief usage examples when absolutely necessary
- Reference actual code files instead of duplicating implementation
- Update screenshots or diagrams if they've changed
- Cross-reference related documentation
- Remove deprecated information
- Add migration notes for breaking changes

## Code Documentation Rules:

- **NEVER duplicate code implementation in docs**
- Reference functions/files like: `functionName()` in `src/path/to/file.ts`
- Use pseudo-code for architectural explanations
- Keep code examples minimal and focused on usage patterns
- Always point readers to actual source code for implementation details
- Remove any existing code duplication and replace with references

## Context:

Review the recent changes in the codebase to identify what documentation needs updating and ensure all information remains accurate and helpful.
