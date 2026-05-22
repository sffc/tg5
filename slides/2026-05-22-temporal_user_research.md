---
marp: true
theme: default
paginate: true
footer: 'TC39 Temporal User Research'
---

<!-- 
_class: lead 
_backgroundColor: #2c3e50
_color: #ffffff
-->

# Temporal User Research
## Shaping the Proposal through Community Feedback

### Shane F Carr & Temporal Champions

---

## Why User Research for Temporal?

- `Date` has been a long-standing pain point in ECMAScript.
- Temporal is a large, complex API aimed at fixing these pain points.
- To ensure developer ergonomics, the champions needed to understand real-world use cases and preferences.
- We employed multiple methods:
  - General usability surveys.
  - Targeted interviews with non-Gregorian calendar developers.
  - Community polling for specific design decisions.

---

## The Naming Impasse

- One of the most debated topics was naming the types without time zones (e.g., what is now `PlainDateTime`).
- Initial names like `LocalDateTime` and `DateTime` caused confusion.
- Champions agreed a prefix was needed for clarity and consistency across `Date`, `Time`, and `DateTime`.
- But which prefix?

---

## Alternatives Considered

- **Civil**: Strong contender, but some found it confusing.
- **Local**: Rejected as confusing and too similar to "Locale" for non-native speakers.
- **Naive**: Used in Python, but raised inclusivity concerns (implying ignoring time zones is "naive").
- **Floating**: Avoided confusion with floating-point arithmetic but felt long.
- **Abstract**: Vetoed as it implies inheritance.

---

## GitHub Discussion: Rationale and Objections

- **The "Think Twice" Strategy**: Champions suggested `PlainDateTime` to make users "think twice" before using it, steering them toward the safer, zoned type (`ZonedDateTime`) to avoid DST bugs.
- **Debate on "Negative" Names**: Some objected to names like `Plain` and `Zoneless`, arguing that naming a class after what it lacks is bad design. They preferred positive names like `Abstract` or `Calendar`.
- **Discoverability**: A pattern of `DateTime` (zoned) and `XxxDateTime` (unzoned) was favored to guide users to the correct choice.

---

## The Twitter Poll

- To break the impasse, champions decided to let the community choose.
- A Twitter poll was run with options agreed upon by the champions:
  - **Plain**
  - **Civil**
  - **Naive**
  - **Floating**
- This was a direct attempt to gather broad community feedback on a contentious design choice.
- Links to the polls:
  - [Poll Thread](https://x.com/justingrantjg/status/1308619968632688640)
  - [Poll Results](https://x.com/justingrantjg/status/1316190780373958656)

---

## Poll Screenshots

![Poll Thread](./assets/2026-05-22/Screenshot%202026-05-22%2008.10.42.png)
![Poll Results](./assets/2026-05-22/Screenshot%202026-05-22%2008.10.55.png)

---

## Poll Results

- The community response was decisive.
- **"Plain"** emerged as the clear winner.
- Other options like Floating and Civil were tied for a distant second.
- This led to the adoption of `PlainDate`, `PlainTime`, and `PlainDateTime`, returning to an early naming concept in Temporal.

---

## Integrating Community Feedback

- **Listening to Objections**: Champions acknowledged community concerns about "negative" names (like `Zoneless` or `Plain`) and balanced them against discoverability goals.
- **Breaking Deadlocks**: Handed the decision to the community via the Twitter poll to resolve a deadlock among valid technical choices.
- **Empowering Users**: Directly adopted "Plain" based on the poll result, demonstrating that community voice directly impacts API design.

---

## Calendar User Studies

- To ensure Temporal worked well for the global community, champions conducted interviews with developers of non-Gregorian calendar applications.
- Focused on developers working with Hebrew, Hijri, and Persian calendars.
- Aimed to understand how these calendars are used in day-to-day life and code.

---

## Key Findings: Hebrew Calendar

- **Developer Pain Points**:
  - Constant conversions between Gregorian and Hebrew calendars needed.
  - Hacky workarounds required for missing API features (e.g., looping through Gregorian dates to find the length of a Hebrew month).
- **Takeaway**: Need for direct API support for calculations in non-ISO calendars.

---

## Key Findings: Persian & Hijri Calendars

- **Developer vs. User Reality**:
  - Users live in the Persian calendar; developers are forced to use Gregorian because databases require it.
- **Lunar Calendar Complexities**:
  - Hijri calendars often need manual corrections (-2 to +2 days) due to moon sightings.
- **Takeaway**: API must allow explicit calendar selection and handle custom/adjusted calendars.

---

## Impact on the Proposal

- **First-Class Non-ISO Calendars**: Developers can perform operations directly in their preferred calendar system.
- **Prefix Consistency**: `Plain` applied to `Date` and `Time` as well as `DateTime` based on feedback.
- **Ergonomics**: Real-world hacks informed the need for comprehensive operations in all supported calendars.

---

## Conclusion

- User research was not just an afterthought; it actively resolved design deadlocks.
- Polling gave the community a voice in naming.
- Interviews ensured the API is robust for global use cases.
- Temporal is a better API because of this engagement.

---

## Primary Sources

- **GitHub Issue #707**: Bikeshedding name of LocalDateTime [Link](https://github.com/tc39/proposal-temporal/issues/707)
- **Twitter Poll Thread**: Initial naming poll [Link](https://x.com/justingrantjg/status/1308619968632688640)
- **Twitter Poll Results**: Final results [Link](https://x.com/justingrantjg/status/1316190780373958656)
- **Meeting Minutes**:
  - [Oct 1, 2020](https://github.com/tc39/proposal-temporal/blob/main/meetings/agenda-minutes-2020-10-01.md)
  - [Oct 8, 2020](https://github.com/tc39/proposal-temporal/blob/main/meetings/agenda-minutes-2020-10-08.md)
  - [Oct 15, 2020](https://github.com/tc39/proposal-temporal/blob/main/meetings/agenda-minutes-2020-10-15.md)
- **Calendar Interviews**: Qualitative research [Link](https://docs.google.com/document/d/1ZTuBbtAHv6gShFiojM7qMJt6-GCIj8JVSsRrM8xJzDI/edit#heading=h.g97xe2z5n4tv)
