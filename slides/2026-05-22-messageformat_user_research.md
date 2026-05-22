---
marp: true
theme: default
paginate: true
footer: 'TC39 MessageFormat 2 User Research'
---

<!-- 
_class: lead 
_backgroundColor: #2c3e50
_color: #ffffff
-->

# MessageFormat 2 User Research
## Demonstrating Readiness Through Empirical Evidence

### TC39-TG5

---

## Why User Research for MessageFormat 2?

- MF2 is a major revision of MessageFormat 1.0, aiming for better expressivity and usability.
- Adding `Intl.MessageFormat` to JavaScript is a significant responsibility for TC39 due to strict backward compatibility.
- To ensure MF2 meets the needs of web developers and avoids potential pitfalls, TC39 requested user studies.
- The goal was to validate the design with real users before full stabilization.

---

## The Process: MessageFormat Arena

- Developed a custom web application: **MessageFormat Arena**.
- Enabled remote, browser-based think-aloud interviews.
- Participants could write or translate messages and see live rendering or test results.
- This structured environment allowed for consistent data collection and observation of real-time problem-solving.

---

## Targeting Key Stakeholders

- The study recognized two distinct groups involved in localization:
  1. **Software Engineers**: Responsible for writing messages and handling logic (e.g., plurals, selections) in the source code.
  2. **Translators**: Responsible for adapting messages to target locales without breaking the code.
- Studying both groups ensured the API works for the entire localization workflow.

---

## Study Structure: Readability & Writability

- **Comprehension Tasks**: Multiple-choice questions to assess if participants could understand MF2 messages without prior training.
- **Writing Tasks**: Software engineers wrote MF2 messages from scratch to match specifications and pass tests.
- **Translation Tasks**: Translators translated existing English MF2 messages into their native languages.

---

## Friction Points Identified

- **Readability**: Translators found the `.match` syntax puzzling, as it relies on programming concepts they were less familiar with.
- **Writability**: Software engineers noted that the lack of nested matching led to repetitive code in complex selection tasks.
- **Syntax Quirks**: The use of the pipe symbol (`|`) for literals was non-intuitive for developers used to quotes.

---

## Locale-Specific Edge Cases

- The study uncovered real-world localization challenges that tested the limits of the syntax:
  - **Turkish**: Suffixes depending on the pronunciation of numbers in timestamps.
  - **Danish**: Ordinals written as words depending on context.
- These cases demonstrated that no static syntax can cover all global linguistic rules out-of-the-box.

---

## Impact on the Proposal

- **Validation of Core Design**: The core syntax was found to be approachable and learnable by both groups.
- **Confirmed Extensibility**: The identified locale issues proved that MF2's **function registry** is essential. These issues can be solved by adding functions rather than complicating the core syntax.
- **Tooling Priority**: Highlighted that translators rely heavily on GUIs, emphasizing that a mature ecosystem is critical for success.

---

## Conclusion

- The user research provided the empirical evidence needed to demonstrate MF2's readiness.
- It moved the discussion from theoretical design to real-world usability.
- It guided the committee to focus on the ecosystem (functions and tooling) to ensure successful adoption.
- MessageFormat 2 is a better, more grounded proposal because of this research.
