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
- User research has become a critical tool to propel proposals forward by:
  - Guiding design decisions.
  - Validating usability before locking in designs.
  - Ensuring global inclusivity for all developers and users.

---

## Case 1: Temporal - The Naming Debate

- `Date` is a long-standing pain point; Temporal fixes it but introduces new concepts.
- A major challenge was naming types without time zones (e.g., `LocalDateTime` vs `CivilDateTime`).
- Champions wanted to guide users away from unsafe use (Justin Grant's "think twice" strategy, Issue #707).
- Community members debated various naming strategies, including `Plain`, `Zoneless`, and `Abstract`.

---

## Temporal: Polling to Guide Design

- Selecting a prefix for types without time zones was contentious, with strong arguments for `Civil`, `Local`, and `Plain`.
- To move forward, champions agreed on a shortlist and turned to the community via a structured Twitter poll.
- Options included `Plain`, `Civil`, `Floating`, and `Other` (Naive was considered but replaced by 'Other' in the final poll).
- This research **guided a critical design decision** by empowering the community to resolve a naming impasse, ensuring the final API resonated with developers.

---

## Temporal: Poll Screenshots

<img src="./assets/2026-05-22/Screenshot%202026-05-22%2008.10.42.png" width="400" />
<img src="./assets/2026-05-22/Screenshot%202026-05-22%2008.10.55.png" width="400" />

---

## Temporal: The Winner Is...

- **`Plain`** won decisively in the community poll, leading to the adoption of `PlainDate`, `PlainTime`, and `PlainDateTime`.
- It demonstrated that community voice could directly resolve naming impasses.
- However, relying on a Twitter poll has downsides for language design:
  - Selection bias toward active social media users and specific networks.
  - No data on whether users actually understand the implications of the choice.
- This ad-hoc approach paved the way for more formal, empirical studies discussed later.

---

## Temporal: Ensuring Global Inclusivity

- To ensure Temporal worked well globally, champions interviewed developers of non-Gregorian calendar applications.
- They interviewed developers like **Eze Fiszerman** (Hebrew calendar) and **Omid Rad** (Persian/Hijri calendars).
- Key findings included:
  - Constant conversions and hacky workarounds were needed in current APIs (e.g., looping to find month length).
  - Lunar calendars need manual corrections (moon sightings).
- This confirmed the need for first-class support for operations directly in non-ISO calendars.

---

## Case 2: MessageFormat 2 - Demonstrating Readiness

- MessageFormat 2 (MF2) aims for better expressivity and usability for localization.
- Adding `Intl.MessageFormat` is a permanent commitment, demanding high confidence in its design.
- TC39 requested empirical evidence to demonstrate that MF2 meets the needs of web developers before full stabilization.

---

## MF2: The Process of Empirical Testing

- Developed a custom web app, **MessageFormat Arena**, by the research team from **UC San Diego** (Shun Kashiwa et al., including faculty member Michael Coblenz).
- Powered by `mf2-tools` by **Luca Casonato** and **Nicolò Ribaudo** (TC39 delegates) for editor features.
- Conducted remote, browser-based think-aloud studies.
- Targeted two distinct groups in the localization workflow:
  1. **Software Engineers** (writing messages).
  2. **Translators** (translating messages).
- Observed real-time problem-solving and comprehension without prior training.

---

## MF2: Findings that Guided the Path

- Translators found `.match` (pattern matching) puzzling; engineers found lack of nested matching repetitive.
- The study uncovered issues with Turkish suffixes and Danish ordinals.
- These findings proved that no static syntax can cover all global linguistic rules, validating MF2's **function registry** approach as essential for extensibility.

---

## MF2: Limitations and Learnings

- Limited to 10 participants; missed testing Polish, Japanese, and Arabic.
- How TG5 can improve future user studies:
  - Build a standing pool of volunteer translators.
  - Leverage open-source partnerships for recruiting.
  - Invest in reusable research infrastructure.
  - Find lightweight ways to reach professional developers.

---

## Synthesis: Strengths and Limitations

- Moves discussions from committee opinions to real-world evidence.
- Polls provide quick community input but risk selection bias and lack depth.
- Formal studies offer deep insights but are resource-intensive and hard to scale.
- Success requires investing in reusable research tools and volunteer networks.
- A mature ecosystem of docs and tooling is as critical as the syntax itself.

---

## Conclusion

- User research is no longer just an afterthought in TC39.
- It resolved the naming impasse in Temporal.
- It demonstrated readiness and guided ecosystem priorities in MessageFormat 2.
- By embracing user research, TC39 creates more robust, inclusive, and developer-friendly standards.
