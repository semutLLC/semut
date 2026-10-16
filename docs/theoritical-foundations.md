# Theoretical Foundations of Semut

Status: Working reference
Purpose: Distinguish established scientific concepts, Semut architectural proposals, and unvalidated hypotheses.

## 1. Purpose

Semut is a cybernetics-inspired architecture for representing, composing, observing, and validating bounded systems across domains.

Semut does not claim to invent cybernetics, dynamical systems, control theory, or second-order observation. It seeks to make relevant concepts interoperable through explicit capability contracts.

## 2. Established Foundations

| Foundation | Important contributors | Relevance to Semut |
|---|---|---|
| Dynamical systems | Newton, Poincare, others | State evolution and mathematical transformations |
| Homeostasis | Walter Cannon | Biological regulation and stability |
| Cybernetics | Norbert Wiener, W. Ross Ashby | Feedback, communication, control, regulation |
| General systems theory | Ludwig von Bertalanffy | Cross-domain system descriptions |
| Control theory | Maxwell, Kalman, others | Stability, observability, controllability |
| Second-order cybernetics | Heinz von Foerster, Margaret Mead, others | Observer participation and reflexivity |
| Conversation Theory | Gordon Pask | Learning, teachback, negotiation of understanding |
| Interaction and design cybernetics | Paul Pangaro, Ranulph Glanville, others | Participatory design and conversation |

These traditions overlap but are not identical.

## 3. First-Order Cybernetics

First-order cybernetics focuses on observed systems, including feedback, communication, regulation, and control.

Example:
- A thermostat measures temperature.
- A controller compares measurements with a target.
- Heating changes the room state.
- Feedback informs subsequent control actions.

A system can have feedback without conscious intention.

## 4. Second-Order Cybernetics

Second-order cybernetics examines observing systems, including the role of observers in constructing descriptions and participating in the systems they study.

It is not simply first-order cybernetics plus a human.

Examples:
- Researchers examine how their observations influence an experiment.
- Participants reconsider how goals are defined.
- Learners revise their own models through conversation.

## 5. Conversation Theory

Gordon Pask developed Conversation Theory as an approach to learning and understanding.

Relevant ideas:
- Learning through interaction.
- Demonstrating understanding through teachback.
- Negotiating concepts and explanations.
- Reflecting on how learning occurs.

Semut may explore these ideas for education, participatory systems, and goal alignment.

## 6. Semut Common Representation

Conceptual form:

(I, S, E, B, G) --F--> (O, S')

Where:
- I: Input
- S: State
- E: Environment
- B: Boundary or constraints
- G: Optional goal
- F: Transformation
- O: Observable output
- S': Next state

This is a Semut conceptual representation, not a universal physical law.

Not all systems have intrinsic goals, controllers, or feedback loops.

## 7. Semut's Proposed Engineering Contribution

Semut proposes reusable CapabilityCells with explicit:
- Input/output contracts
- State and ownership
- Boundaries and permissions
- Execution and validation rules
- Failure and escalation behavior
- Timing and resource constraints
- Composition interfaces

Existing scientific theory does not establish that Semut's proposed contracts will work across all domains.

## 8. Levels of Validation

1. Representation validation: Can a domain be meaningfully represented?
2. Composition validation: Can independently implemented cells interoperate while respecting contracts?
3. Outcome validation: Does the resulting system work reliably and usefully?

Passing one level does not imply passing the others.

## 9. Scientific and Architectural Limits

- Common representation does not imply common physical laws.
- Mathematical description does not guarantee predictive accuracy.
- Compatible interfaces do not guarantee safe composition.
- Deterministic checks do not guarantee the truth of nondeterministic outputs.
- Human values and goals need not be objectively quantifiable.
- Cybernetic principles do not explain every aspect of the universe.

## 10. Research Questions

- Which boundaries can be represented consistently?
- Which kinds of state can be shared safely?
- When is a goal meaningful or optional?
- Can first-order and second-order interactions use the same composition framework?
- How do independent participants negotiate goals and constraints?
- What evidence demonstrates practical interoperability?

## 11. References

- Norbert Wiener (1948), Cybernetics: Or Control and Communication in the Animal and the Machine.
- W. Ross Ashby (1956), An Introduction to Cybernetics.
- Ludwig von Bertalanffy (1968), General System Theory.
- Heinz von Foerster (1974), Cybernetics of Cybernetics.
- Gordon Pask (1975), Conversation, Cognition and Learning.
- Paul Pangaro and collaborators (2024), Gordon Pask's Conversation Theory and Interaction of Actors Theory: Research to Practice.

## 12. Semut Documentation Boundaries

- vision-and-validation.md: The vision and testable hypothesis.
- theoretical-foundations.md: Established scientific terminology and intellectual lineage.
- semut-core capability contract documentation: Executable interface and validation requirements.
- systems-lab: Experiments and evidence.

Semut should preserve these distinctions as the project evolves.
