---
name: odf-code-generator
description: ODF-specific code generation skill that produces reliable map code using only APIs verified through official examples, documentation, or type definitions. Disallows unverified assumptions and prevents hallucinations.
alwaysApply: true
globs: ["**/*"]

---

> **Path convention:** Repository paths in this skill are relative to the **workspace root** (monorepo top-level folder). `.continue` and `.opencode` live at that root.

# ODF Rules

## Definition

ODF = an OpenLayers-based web mapping library (not OpenDocument Format)

---

## Top-Level Goals

Follow the priorities below in order:

1. Do not be wrong
2. Use only the public API
3. Answer only based on verified evidence
4. If the user requests code generation, always produce code
5. Keep the search short and precise

Accuracy over speed.  
Evidence quality over explanation volume.  
Executability and verifiability over code size.

---

## Source Roles

- html examples: evidence of actual usage patterns (html/ directory)
- mdx docs: evidence for option meanings, constraints, recommended usage, and defaults (mdx/ directory)
- js/odf.d.ts: evidence for the static contract of the public API
- current code: primary reference for modification tasks
- html/SAMPLES-INDEX.md: starting point for example discovery

Do not confuse the roles of these sources.

---

## Absolute Prohibitions

- Do not use any namespace other than `odf.*` (`ol.*`, `L.*`, `mapboxgl.*`, etc.)
- Do not invent arbitrary API combinations without related examples
- Do not infer runtime behavior from d.ts alone without cross-checking mdx/ docs and html/ examples
- Do not describe optional properties as if they were defaults
- Do not treat internal implementation APIs as public APIs
- If the user asks to modify existing code, do not arbitrarily rewrite the entire structure
- If the user requests code generation, do not stop with explanation only
- Do not repeat meaningless re-search for the same purpose

---

## Public API Principle

- For code generation/modification, use only the public API as documented in js/odf.d.ts and verified in html/ examples
- Even if internal implementation details are discussed, do not use non-exported APIs in generated code

---

## Determining Question / Task Type

### Informational Question Types

- API existence / function signature / callback parameter / return object structure  
  → js/odf.d.ts → mdx/ → html/

- Options / defaults / props / parameters  
  → mdx/ → html/
  - Do not rely on d.ts alone

- Usage examples / feature implementation  
  → html/SAMPLES-INDEX.md → html/ → mdx/ → js/odf.d.ts (only if needed)

- Domain feature questions (SLD, WMS, WFS, Draw, Style, Event, etc.)  
  → domain-keyword-based mdx/ + html/ → js/odf.d.ts

### Actual Task Types

- Add a new feature  
  → html/SAMPLES-INDEX.md → related html/ → mdx/ → js/odf.d.ts

- Modify existing code  
  → current code → related html/ → mdx/ → js/odf.d.ts

- Fix an error  
  → current code / error message → problems → related html/ → mdx/

- Refactoring / structural improvement  
  → current code → verify public API preservation → related html/ → mdx/

- API / usage Q&A  
  → js/odf.d.ts → mdx/ → html/

If both a question type and a task type are present, prioritize the task type.

---

## Determining Whether It Is a Code Generation Request

If the request contains any of the following expressions, treat it as a "code generation request":

- full code
- complete code
- working code
- implementation code
- full example
- full sample
- make it
- write it
- implement it

When it is a code generation request:

- Do not end with explanation only
- Always output a code block
- Even if not fully verified, provide a full code skeleton or minimally runnable code in limited-generation mode (Mode B)
- Keep explanations limited to a short evidence summary before or after the code
- Do not provide an answer without code

---

## Handling Composite Feature Implementation Questions

- If the user's request contains two or more feature steps, treat it as a "composite feature implementation question"
- It must be broken down into subtasks
- Find the required evidence for each step, then recombine them into full code
- Even if there is no single exactly matching example, multiple related examples may be combined
- Combination points must be cross-verified with mdx/ docs and js/odf.d.ts
- Even if some connection points are not fully verified, mark them with TODO/comments and provide the full skeleton
- Do not fall back to an explanation-only answer just because there is no single matching example

### Example of Composite Feature Decomposition

Request:
- On map click
- Create a 500m buffer from the clicked location
- Highlight only features inside the buffer

Breakdown:
1. Capture the click event
2. Create click coordinates or geometry
3. Create the buffer polygon
4. Retrieve the target feature list
5. Apply a spatial filter
6. Apply highlight styling
7. Clear the previous highlight state

---

## Official Example First Rule

- If there is an official example that directly matches the question title/description, read that example first
- Similar examples may be used only as supporting evidence
- Do not generate code from similar examples alone before reading the directly matching official example
- If html/SAMPLES-INDEX.md contains the closest example by title/description, check it first
- Prefer a "directly matching example" over a "roughly similar example"

### Examples of Direct Matches

- DrawControl question → prioritize an example that directly uses DrawControl
- Map click event question → prioritize an example that directly handles map click events
- WMS layer question → prioritize a WMS-related example
- Even for style questions, if they are within the context of a specific control/component, prioritize that component’s example

---

## Same Component Priority Rule

- If the question asks about the behavior of a specific component or control (Map, Layer, DrawControl, etc.), prioritize html/ examples and mdx/ docs that directly use that same component
- Do not replace them with similar examples from other components
- If there is an example for the same component, prefer its internal option/configuration pattern over external post-processing patterns
- For components that manage style/event/state internally, do not arbitrarily intervene through external event post-processing
- Prefer code that matches the official component usage pattern over code that merely seems to work

---

## Search Start Rule

- If html/SAMPLES-INDEX.md exists, check it first
- Prioritize functional similarity over example title
- If there are multiple related examples, follow this priority order:
  1. An official example whose title/description directly matches the question
  2. An example that directly uses the same component
  3. An example that uses only the public API
  4. A safe-as-template example
  5. An example suitable as a minimal-modification starting point
  6. An example in the same domain
  7. A newer / more refined example

---

## Search Budget Limits

Default search limits:

- html/SAMPLES-INDEX.md: once
- html/ examples: up to 2
- mdx/ docs: up to 2
- js/odf.d.ts: up to 1

Exceptions:  
You may add 1 more html/ example and 1 more mdx/ docs file if:

- A directly matching official example is discovered late
- An additional same-component example is needed
- There is a pattern conflict between examples
- A key step is missing in a composite feature question

Rules:

- Do not repeat searches for the same purpose
- Stop searching if no new information appears
- End immediately once sufficient evidence is secured
- Even if the search budget is exhausted, if verification is still insufficient, output in Mode B or C rather than A
- The search budget must not be used as an excuse to skip a core example

---

## Example Search Rules

- Read the single most relevant html/ example first
- For code generation/modification questions, checking related examples takes priority
- If an example is large, read only the necessary sections
- If patterns conflict between examples, cross-check with mdx/ docs
- Do not overwrite the current code with the entire example as-is
- Examples are evidence for modification or a starting point for implementation
- Do not first infer from a similar example and then ignore a more directly matching official example later

---

## Docs Search Rules

- For feature/domain questions, check at least one mdx/ docs file
- Docs are for verifying option meanings, constraints, defaults, and recommended usage
- Do not generalize descriptive sentences as-is; use only the parts directly relevant to the actual question
- Do not conclude runtime behavior from docs if it is not stated there
- For questions about a specific component, prioritize the mdx/ docs for that component

---

## js/odf.d.ts Search Rules

- Use it to verify API existence / function signatures / callback parameter shapes / return types
- Do not determine runtime defaults, side effects, or event trigger conditions from d.ts alone
- If an API appears only in d.ts and is not verified in html/ examples or mdx/ docs, do not use it for code generation
- d.ts does not replace html/ examples or mdx/ docs

---

## Current Code First Rule

- If the user asks to modify existing code, read the current code first
- Preserving the existing structure with minimal changes is the default principle
- Preserve the existing public API pattern, state flow, and event flow as much as possible
- Do not perform unrequested refactoring, file splitting, or large structural changes

---

## Feature Implementation Keyword Rule

- Do not search using action verbs alone
- Search domain keywords first, then combine them with action keywords
- If the first attempt fails, only one synonym-based re-search is allowed
- After that, do not repeat searches without new keywords

Examples:
- download → save, export, blob, file, xml
- click → select, event, listener, feature, popup
- draw finish → drawend, complete, finish, geometry
- highlight → style, select, active, feature, render

---

## Value / Default Tracking Rules

- If a value comes from a variable/constant/config/parent class, trace it to the final declaration
- If `undefined`, `null`, `??`, or `||` is found, move to the definition location
- Do not guess external library defaults before confirming internal values
- Do not interpret optional notation as a default value

---

## grep Rules

- For large files, grep first and then read only the necessary parts
- If a call site is found, move to the definition site
- Verify the structure around the definition
- Do not repeatedly reread the full same file
- Stop if no new information appears

---

## Verification Rules for Spatial Operations / Style / Selection Implementation Questions

Do not conclude after checking only a single API for questions involving:

- buffer
- contains
- intersects
- within
- extent
- geometry operations
- highlight
- style changes
- selection/filter

Do not finish before verifying at least two of the following:
1. Evidence related to geometry/buffer
2. Evidence related to feature selection/filter
3. Evidence related to style/highlight

- Do not assume the whole implementation is possible just because geometry/buffer was confirmed
- If highlight or selection flow is not verified, output in Mode B and mark it with TODO comments

---

## Rules for Combining Examples

- Even if there is no single matching example, related examples may be combined
- Conditions:
  1. Each example is based on the public API
  2. The combined API usage does not conflict with mdx/ docs and js/odf.d.ts
  3. Unverified connection points are explicitly marked with TODO/comments
  4. It has been confirmed that no directly matching official example exists

- If a directly matching official example exists, do not combine only similar examples
- Do not fall back to an explanation-only answer just because a single example is missing

---

## Code Generation Principles

- Start from a related example whenever possible
- Prefer copying the example code as-is and applying only minimal modifications
- Prioritize the API chain used in the example
- Do not guess unverified APIs/options/event structures
- Confirm callback parameters / return objects / option structures in html/ examples first, and supplement with js/odf.d.ts only if needed
- Do not guess the full event object shape
- Only use event access patterns directly verified in html/ examples
- When combining external libraries, separate the ODF section from the general JS / external library section
- Do not overwrite internally managed behavior with external post-processing code
- Prefer code that matches official usage patterns over code that merely seems likely to work

```javascript
// ✅ Allowed
layer.addFeature(feature)
odf.event.addListener(obj, 'eventName', fn)

// ❌ Forbidden
layer.getSource().addFeature(feature)