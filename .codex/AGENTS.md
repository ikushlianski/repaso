# Development Rules and Guidelines

## Modes

You can act either in planning or in development mode. The user decides what mode you're in, but if not explicitly stated, default to implementation mode.

When in planning mode, I'd like you to ask any questions directly in the planning doc files you output. Inform me if you have questions and I will answer inside those docs.

## Code Style and Standards

### File Naming and Structure

- Use kebab-case for filenames with entity specification (e.g., `create-gps-order.handler.ts`)
- Never create classes - use exported functions only
- Group by use cases with co-located handlers, adapters, controllers, derivers, and repositories
- Adapter naming: postfix with purpose (`.adapter.ts`, `.eb.ts`, `.http.ts`)

### Code Quality

- Files should be under 300 lines, ideally around 150
- Never use `any` type - grep codebase for suitable types
- Use TypeScript path aliases when configured
- Prefer Zod for runtime validation and type schemas
- Remove and omit all code comments
- Use `console.log` for logging (not loggerWithCorrelationId)

### Dependencies and Imports

- Use shared-lib for types common between backend and frontend
- Never modify eslint, prettier, tsconfig files except for installing dependencies

## Testing Standards

### Testing Approach

- Always co-locate tests with the file being tested (no `__tests__` folder)
- Use Vitest for logic testing, React Testing Library for components
- Group tests in logical `describe` blocks with `it` or `should` statements
- Omit all comments

### Mock Standards

- Run tests: `npx vitest run` or `npx vitest run specificFile.test.ts` from root

## React Component Guidelines

### Component Structure

- Extract testable logic into small simple sync functions (hooks or plain TypeScript functions)
- Always write tests for extracted plain functions
- Create multiple small components instead of a single giant one
- Ensure rendering result respects current styling rules/theming
- Componentize complex UI logic for better testability and maintainability

### Naming Conventions

- PascalCase for component names (e.g., `OrderList`, `UserProfileCard`)
- Kebab-case filenames matching component name (e.g., `order-list.tsx` for `OrderList`)
- Do not use PascalCase for filenames
- Name default exports with the component name, not `default`
- For small, co-located components, prefix with parent component name (e.g., `order-list-item.tsx` for `OrderListItem` inside `OrderList`)
- Avoid generic names like `Component` or `MyComponent`
- Suffix hooks with `use` (e.g., `use-order-list.ts`), but never for components

## Next.js Guidelines

### Component Architecture: Server-First Approach

- **Prioritize Server Components**: Default to server-side rendering for all components
- Minimize client-side JavaScript by keeping most logic on the server
- Use client components (`'use client'`) ONLY when absolutely necessary
  - Interactive elements requiring browser APIs
  - Components with client-side state management
  - Event-heavy interactions
- Create thin client components that delegate most logic to server components
- Use `React.lazy()` and `next/dynamic` for truly optional client-side components

### Project Structure

- Implement feature-based or domain-driven folder structure
- Keep pages minimal, delegate complex logic to server and client components
- Utilize Next.js 13+ app directory with clear server/client component separation
- Separate data fetching logic from rendering logic
- Organize components by responsibility: server-first, then client-side

### Performance and Optimization

- Leverage Server Components for maximum performance
- Use Static Site Generation (SSG) and Incremental Static Regeneration (ISR)
- Implement aggressive code splitting
- Minimize client-side JavaScript bundle size
- Cache aggressively at the server component level
- Use `next/dynamic` for truly optional, heavy client-side components

### Data Fetching Strategies

- Prefer server-side data fetching methods
- Use React Server Components for data fetching
- Implement `async` server components for direct database/API calls
- Use `cache()` and `revalidate` for intelligent server-side caching
- Handle loading states with React Suspense
- Implement efficient data fetching patterns with minimal client-side overhead

### API Routes and Middleware

- Keep API routes thin and focused
- Implement comprehensive middleware for cross-cutting concerns
- Validate and sanitize all inputs on the server
- Secure routes with robust authentication checks
- Use server-side validation libraries (Zod, Yup)

### Styling and Theming

- Leverage CSS modules or server-compatible styling solutions
- Implement theme generation on the server
- Ensure responsive design with server-side calculations
- Follow strict accessibility guidelines
- Minimize client-side style computations

### Rendering Principles

1. Start with server components
2. Add client components sparingly
3. Use server components for data fetching
4. Minimize client-side state
5. Leverage React Server Components for performance
6. Use streaming SSR for faster initial page loads
7. Implement progressive enhancement

### Advanced Patterns

- Use `React.cache()` for intelligent server-side memoization
- Implement partial prerendering for dynamic content
- Use server actions for mutations
- Create thin, lightweight client components
- Optimize critical rendering path

## Database operations

When changing schemas in DB ORM, never run migrations against any database, be it dev or production environment. You are free to generate migration files though.

## Communication and Planning

### Step-by-Step Approach

- Always output implementation plan before starting (business/app logic only)
- Break down larger pieces into separate steps
- Check TypeScript and logic after changes
- Never create markdown plan files in codebase

### User Interaction

- When discussing options, investigate and ask architectural questions before implementing
- For refactoring: run `pnpm precommit:dryrun` and `pnpm test:ci` after changes
- Skip dev server attempts unless instructed
- Double-check all import usages when refactoring

## After any change

- Always recheck types and tests in Typescript once you are done refactoring
- There are no unrelated type errors. If you see any, fix them immediately. Do not use hacks like `any` or other workarounds that junior devs would do
- Double-check all usages when refactoring imports/functions

## Spec-Driven Development (Critical)

Always ask the user if we're in planning mode or in implementation mode if not obvious from the user's query.

### Task Management System

- Follow three-step pipeline: Requirements (user story) → Technical Design (architecture/specs) → Implementation (dev work, separate chat)
- Create only ONE user story per message in planning mode, but include product and architectural questions inside the respective docs under the story (see below)
- Always ask clarifying questions
- Wait for user confirmation before starting to implement something

### Implementation Pipeline

- Step-by-step implementation (one subtask at a time)
- Keep updating the architecture and spec docs as we move through the actual implementation
- Complete quality gates before marking subtasks complete
- Write unit tests, verify integration, check linting

### Folder Structure for Tasks

```
todos/
└── 030-billing-milestone/
    └── 0001-billing-system-story/
        ├── story.md                             # User story
        ├── spec.md                              # Technical specifications
        ├── progress.md                          # AI progress on this folder (task)
        ├── architecture.md                      # System design (if required)
        └── tasks.md                             # Implementation tasks
```

### spec.md

This file has an approved boolean field at the top, which defaults to false.

### story.md

This file has an approved boolean field at the top, which defaults to false.

### progress.md document

This document must be initially created with the following content:

```markdown
- [ ] Architecture questions created
- [ ] Architecture questions answered, decisions written
- [ ] AI reviews decisions, does one more pass of discussion
- [ ] Spec is approved by user
- [ ] User story is approved by user
- [ ] `tasks.md` updated with the most relevant tasks
- [ ] Task implementation started (see `./tasks.md`)
- [ ] Task implementation completed
```

As we discuss the initial architecture, we turned a chance into the decision made. A decision is just one or two sentences next to the question. This will be the basis for various decisions that were made in the project.

### Documentation Style

- Apply humanizer approach: natural conversation tone, no AI markdown formatting
- Keep technical depth but strip unnecessary complexity
- Use bullet points sparingly, prefer plain text
- Follow Google's technical writing best practices

Milestones use three-digit numbering (010, 020, 030) with space
for priority insertions (015, 025). User stories follow
US001-descriptive-name format, and tasks use 0001-task-name.md
with subtasks numbered as ### 0001.1 Subtask Name.

AI Work Rules

The system enforces strict one-by-one processing to prevent
rushing and ensure quality:

- Create only ONE user story per message, then wait for approval
- Create only ONE task per message, then wait for approval
- Ask clarifying questions immediately when anything is unclear
- Never make assumptions about requirements or technical details
- Use the format "Before creating [item], I need clarification
  on:" followed by numbered questions

Task Structure Requirements

Each task file must include:

- Title using heading format
- Overview with brief implementation description
- Acceptance Criteria with measurable success conditions and
  checkboxes
- Subtasks using ### numbering format with progress checkboxes
- Clear traceability back to user story requirements

Implementation Flow

The system requires asking the user about anything unclear, then
sequentially creating milestone folders, user story folders,
task files, and finally subtasks within each file. Everything
must link back to original requirements for full traceability.

This approach prevents scope creep, ensures thorough planning,
and maintains clear documentation throughout the development
process.

## Git Safety and Privacy Rules

### Git Operation Safety (CRITICAL)

- **NEVER push to remote repositories unless explicitly requested**
- **NEVER run `git push` automatically** - always ask permission first
- **Only commit when user specifically asks** - never auto-commit
- **Always ask before any destructive git operations** (reset, rebase, force push)
- When creating commits, use the exact format specified in system instructions
- If commit fails, retry once; if it fails again, ask user to check configuration

### AI Usage Privacy (For Public Repositories)

- **Never mention AI tools** in commit messages, code comments, or documentation
- **Never add comments like "Generated by Claude"** or "AI-assisted"
- **Write natural-looking commit messages** that reflect your normal development style
- **Review and refactor AI-generated code** to match your personal coding patterns

### Git Workflow Guidelines

- Use descriptive, natural commit messages without AI references
- Keep commits atomic and focused on single changes
- Follow existing commit message patterns in the repository
- Ask permission before creating new branches or switching branches
- Never commit sensitive information (API keys, passwords, private configs)
- Respect existing `.gitignore` patterns and suggest additions when needed

### Branch Management

- Ask before creating or switching branches
- Use clear, descriptive branch names
- Follow project branching conventions if they exist
- Never force push without explicit permission

### Commit Message Best Practices

- Use imperative mood ("Add feature" not "Added feature")
- Keep first line under 50 characters
- Use conventional commit format if project uses it
- Never mention AI tools or assistance
- Focus on the "what" and "why" of changes

## Quality Gates (Must Pass before you finish any task)

- [ ] Code compiles without errors
- [ ] All tests pass
- [ ] No linting violations
- [ ] Proper error handling implemented
- [ ] Types are correct and safe
- [ ] Integration with existing code is seamless

===========================

## AI Development Pipeline

### Source of tasks

See the /todos folder.

### PIPELINE EXECUTION RULES

**NEVER** declare a task complete based on your own assessment. A task is ONLY complete when the verification script exits with code 0. If verification fails, continue working until it passes.

### Commit Strategy

After each verified step:

    git checkout -b ai-task-{task_id}-$(date +%s)
    git add .
    git commit -m "✓ Step {N}/{TOTAL}: {description} [VERIFIED]"
    git tag "rollback-step-{N}-$(date +%s)"

If verification fails:

    git reset --hard "rollback-step-{N-1}-*"

### Task Execution Loop

For each step:

1. Read complete context bundle (a task from todos folder that I gave you)
2. Implement required changes
3. Run verification command
4. If verification fails (exit code ≠ 0):
   - Analyze failure output
   - Fix the issue
   - Return to step 3
5. Only when verification passes: commit and move to next step

### Failure Handling

If a step fails 3+ verification attempts:

1. Revert to last successful checkpoint
2. Document failure in failure_log.md that's in docs-framework/progress folder.
3. Create detailed failure report with attempted changes and verification output, commit the report

### Progress Reporting

After each step, update progress.md of the task folder. If the file does not exist, create it:

    ## Task Progress: {task_id}
    - [x] Step 1: {description} - VERIFIED ✓
    - [ ] Step 2: {description} - IN PROGRESS
    Current branch: {branch_name}
    Rollback point: {tag_name}

### Verification Requirements

Before declaring ANY task complete, run:

- `precommit hook`: Look for precommit hooks in the project (package.json) and run those if exist
- `syntax_check`: Otherwise run linting and type checking (npm run typecheck is the most typical one)
- `unit_tests`: Run all test suites
- `integration_tests`: Run end-to-end behavior tests if present in the repo
- `manual_verification`: Run custom verification scripts if the user has instructed you

**Remember:** Your job is to make code work correctly, not to finish quickly. Each step must be genuinely complete and verified. You are free to execute any non-destructive commands and perform web search.
