---
marp: true
theme: default
paginate: true
footer: 'TC39 User Research: Propelling Proposals'
---

<!-- 
_class: lead 
_backgroundColor: #2c3e50
_color: #ffffff
-->

# Propelling TC39 Proposals Through User Research
## Evidence from Temporal and MessageFormat 2

### TC39-TG5

---

## The Evolving Role of User Research in TC39

- Historically, language design has often relied on committee consensus and expert opinion.
- As the web platform grows, proposals become larger and more complex.
- **Thesis**: User research has become a critical tool to propel proposals forward by:
  - Breaking design deadlocks.
  - Validating usability before locking in designs.
  - Ensuring global inclusivity for all developers and users.

---

## Case 1: Temporal - Breaking Deadlocks

- `Date` has been a long-standing pain point in ECMAScript.
- Temporal introduces a large, complex API to fix it.
- **The Naming Impasse**: Champions were deadlocked on naming types without time zones (e.g., `LocalDateTime` vs `CivilDateTime` vs `PlainDateTime`).
- Justin Grant suggested `PlainDateTime` to discourage accidental use over safer zoned types (Issue #707).

---

## Temporal: The Power of Community Polling

- To break the deadlock, champions turned to the community via structured Twitter polls run by Justin Grant (Sept/Oct 2020).
- Options were agreed upon by champions: **Plain**, **Civil**, **Naive**, **Floating**.
- **Result**: "Plain" won decisively, as recorded in meeting minutes (Oct 15, 2020).

---

## Temporal: Poll Screenshots

<img src="./assets/2026-05-22/Screenshot%202026-05-22%2008.10.42.png" width="400" />
<img src="./assets/2026-05-22/Screenshot%202026-05-22%2008.10.55.png" width="400" />

---

## Temporal: Ensuring Global Inclusivity

- To ensure Temporal worked well globally, champions interviewed developers of non-Gregorian calendar applications.
- **Credit**: Interviews with developers like **Eze Fiszerman** (Hebrew calendar) and **Omid Rad** (Persian/Hijri calendars).
- **Findings**:
  - Constant conversions and hacky workarounds were needed in current APIs (e.g., looping to find month length).
  - Lunar calendars need manual corrections (moon sightings).
- **Impact**: Confirmed the need for first-class support for operations directly in non-ISO calendars.

---

## Case 2: MessageFormat 2 - Demonstrating Readiness

- MessageFormat 2 (MF2) aims for better expressivity and usability for localization.
- Adding `Intl.MessageFormat` is a permanent commitment, demanding high confidence in its design.
- TC39 requested empirical evidence to demonstrate that MF2 meets the needs of web developers before full stabilization.

---

## MF2: The Process of Empirical Testing

- Developed a custom web app, **MessageFormat Arena**, by the research team from **UC San Diego** (Shun Kashiwa et al.).
- Powered by `mf2-tools` by **Luca Casonato** (a TC39 delegate) for editor features.
- Conducted remote, browser-based think-aloud studies.
- Targeted two distinct groups in the localization workflow:
  1. **Software Engineers** (writing messages).
  2. **Translators** (translating messages).
- Observed real-time problem-solving and comprehension without prior training.

---

## MF2: Findings that Guided the Path

- **Friction Points**: Translators found `.match` (pattern matching) puzzling; engineers found lack of nested matching repetitive.
- **Locale Edge Cases**: Uncovered issues with Turkish suffixes and Danish ordinals.
- **Impact**: Proved that no static syntax can cover all global linguistic rules, validating MF2's **function registry** approach as essential for extensibility.

---

## Synthesis: How User Research Propels Proposals

- **From Theory to Practice**: Moves discussions from committee opinions to real-world evidence.
- **Empowering the Community**: Polls and interviews give direct voice to developers, ensuring the language serves them.
- **Guiding Ecosystem Development**: Highlights that a good proposal needs a mature ecosystem (docs, tooling) as much as good syntax.

---

## Conclusion

- User research is no longer just an afterthought in TC39.
- It actively resolved deadlocks in Temporal.
- It demonstrated readiness and guided ecosystem priorities in MessageFormat 2.
- By embracing user research, TC39 creates more robust, inclusive, and developer-friendly standards.
