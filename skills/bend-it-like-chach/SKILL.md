---
name: bend-it-like-chach
description: Write and refactor React and Next.js interfaces using the user's preferred style of component composition, explicit types, data-driven rendering, scoped CSS, and semantic HTML. Use when implementing or modifying React UI for this user.
---

# React coding style

Write React code that makes the structure, responsibilities, and dependencies of the interface easy to understand and change.

## Work within the project

- Read the project instructions and relevant surrounding code before making changes. Follow the project's framework version, tooling, and established conventions.
- Apply these principles within the requested scope. Do not reorganize unrelated code or replace an established styling system merely to match this skill.
- When refactoring, preserve content, behavior, accessibility, and responsive layouts unless the user requests a change.

## Compose meaningful components

- Make pages and routes read like an outline of the interface. Give major sections named components that own their markup and section-specific concerns.
- Extract repeated interface concepts into named components when doing so clarifies their purpose, even if they currently have only one parent. Avoid components that add indirection without making the code easier to understand.
- Group a component and its styles in a dedicated directory when that fits the project. Use descriptive component and file names.
- Pass dependencies through explicit props. Keep content and configuration close to the component that owns them unless multiple parts of the application need them.
- Keep reusable components flexible where context matters. For example, an image component should allow appropriate alternative text instead of imposing the same text in every context.

## Represent repetition as data

- Describe repeated content as typed data and render it with a shared component and `map`, rather than duplicating substantial JSX.
- Keep data near its owning section unless there is a reason to share it. Use stable, meaningful keys for rendered lists.
- Keep the relationship between data and markup easy to see. Avoid adding a configuration framework for simple, fixed content.

## Make types and interfaces clear

- In TypeScript projects, use named, descriptive types for component props and structured data. Use `import type` for type-only imports.
- Follow the project's existing type organization. For a new project, a shared `types.ts` can serve as a central place for component contracts and shared content types.
- Share a type when it represents a genuinely shared concept; avoid tying unrelated components together just because their props currently have the same shape.
- Avoid maintaining duplicate definitions of the same contract. Let TypeScript infer straightforward local values when an annotation would add no useful information.

## Keep styles close to their owners

- When free to choose a styling approach, prefer CSS Modules alongside components for section-specific styles.
- Keep truly shared foundations—such as design tokens, resets, layout containers, and common button styles—in a shared stylesheet.
- Keep responsive rules with the styles they modify where practical. When moving styles into CSS Modules, update the corresponding selectors and breakpoints so they still target the rendered elements.
- Preserve the project's existing styling approach when it has already chosen one.

## Use meaningful HTML

- Choose elements for their actual document meaning, not merely for styling. For example, use an ordered list for a sequence of steps and native `details` and `summary` for a simple disclosure.
- Preserve meaningful headings, landmarks, accessible names, keyboard interactions, and focus states. Use ARIA where it adds the necessary semantics.
- Treat decorative imagery as decorative, and provide context-appropriate alternative text for meaningful imagery.

## Write readable React

- Format JSX and structured data so nesting, attributes, and component boundaries are easy to scan. Avoid packing entire sections onto single lines.
- In frameworks with server components, keep static components server-renderable and place client boundaries around the parts that need interactivity.
- Keep interactive state close to where it is used, and derive values from existing state rather than duplicating it.

Verify the changed interactions, semantics, and affected responsive layouts, and run the project checks appropriate to the change.
