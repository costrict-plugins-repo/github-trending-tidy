# tidy

A Claude Code plugin for plan-driven TDD development with Tidy First principles.

## Name

**tidy** — Plan-driven TDD execution with Tidy First principles.

## Description

tidy provides an interactive TDD workflow powered by Kent Beck's Tidy First approach. You write a plan (a markdown checklist of small tasks), then execute them one by one through a strict Red → Green → Refactor cycle.

The plugin acts as a "Genie" — it executes your commands (`go`, `refactor`, `commit`) but never makes strategic decisions on its own. You stay in control of what to build, when to tidy, and when to commit.

**Key features:**
- **go**: Write a failing test, then write the minimum code to pass it. One task at a time.
- **refactor**: Apply one Tidy First pattern (Guard Clause, Extract Method, Rename, etc.) and verify tests still pass.
- **commit**: Commit with strict separation — structural changes and behavioral changes never mix.
- **Built-in Tidy First patterns**: 11 tidying patterns with prioritization (eliminate duplication → improve clarity → reduce complexity).
- **Context-constrained**: Only loads the current task, never the full plan. Keeps the conversation focused.

## Example Use Cases

### Solo TDD workflow
```
/tidy:augmented-coding
> Select plan → go → commit → refactor → commit → go → ...
```
Write a plan with small tasks, then let tidy guide you through Red-Green-Refactor for each one.

### Tackling a large feature
Break a feature into 10-30 minute tasks in a plan file, then execute them sequentially. tidy tracks progress with checkboxes and always shows you what's next.

```markdown
# User Authentication

## TDD Plan

### Phase 1: Domain
- [x] **Task 1.1**: Password value object with validation
- [ ] **Task 1.2**: User entity with email and password
- [ ] **Task 1.3**: User repository interface

### Phase 2: Service
- [ ] **Task 2.1**: Registration service
- [ ] **Task 2.2**: Duplicate email check
```

### Keeping code clean during development
After a few `go` cycles, the code starts to smell. tidy recommends `refactor` when it detects bloated functions, duplication, or complex conditionals — then applies exactly one tidying pattern per step.

### Pair programming with AI
You make the decisions (what to build, when to refactor, when to commit). tidy executes precisely what you ask — no more, no less. It stops and asks when facing irreversible decisions like new abstractions or dependency additions.

## Install

```
/plugin install tidy@claude-plugins-official
```

## Skills

| Skill | Command | Description |
|-------|---------|-------------|
| augmented-coding | `/tidy:augmented-coding` | Plan-driven TDD execution with go/refactor/commit cycle |
