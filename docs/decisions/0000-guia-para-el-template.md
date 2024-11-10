---
# These are optional metadata elements. Feel free to remove any of them.
status: "{proposed | rejected | accepted | deprecated | … | superseded by ADR-0123"
date: {YYYY-MM-DD when the decision was last updated}
decision-makers: {list everyone involved in the decision}
consulted: {list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication}
informed: {list everyone who is kept up-to-date on progress; and with whom there is a one-way communication}
parent: Architectural Decisions
nav_order: 9
---

# {utilizar un titulo corto}

## Context and Problem Statement

{Describimos la problematica entre 3 o 4 sentencias en forma de pregunta.
How to write readable test assertions?
How to write readable test assertions for advanced tests?}

<!-- PREGUNTAR SOBRE ESTO  --> 
<!-- This is an optional element. Feel free to remove.  --> 
## Decision Drivers

* {decision driver 1, e.g., a force, facing concern, …}
* {decision driver 2, e.g., a force, facing concern, …}
* … <!-- numbers of drivers can vary -->
<!-- PREGUNTAR SOBRE ESTO  --> 

## Opciones consideradas 

* {title of option 1}
* {title of option 2}
* {title of option 3}
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: "{title of option 1}", because {justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.
Opción elegida: "{título de la opción 1}", porque {justificación, p. ej., la única opción que cumple el criterio k.o. del factor de decisión | que resuelve la fuerza {fuerza} | … | resulta mejor (ver más abajo)}.

Chosen option: "Plain JUnit5", because comes out best (see "Pros and Cons of the Options" below).

<!-- HASTA ACA, SI ES NECESARIO SEGUIR PARA MAS DETALLE -->

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good, because tests are more readable
* Good, because more easy to write tests
* Good, because more readable assertions
* Bad, because more complicated testing leads to more complicated assertions
* … <!-- numbers of consequences can vary -->

<!-- This is an optional element. Feel free to remove. -->
### Confirmation

{Describa cómo se puede/deberá confirmar la implementación o el cumplimiento del ADR. ¿El diseño elegido y su implementación están en línea con la decisión? Por ejemplo, una revisión del diseño o del código o una prueba con una biblioteca como ArchUnit pueden ayudar a validar esto. Tenga en cuenta que, aunque clasificamos este elemento como opcional, se incluye en muchos ADR.}

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### {title of option 1}

<!-- This is an optional element. Feel free to remove. -->
{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
<!-- use "neutral" if the given argument weights neither for good nor bad -->
* Neutral, because {argument c}
* Bad, because {argument d}
* … <!-- numbers of pros and cons can vary -->

### {title of other option}

{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
* Neutral, because {argument c}
* Bad, because {argument d}
* …

<!-- This is an optional element. Feel free to remove. -->
## More Information

{You might want to provide additional evidence/confidence for the decision outcome here and/or document the team agreement on the decision and/or define when/how this decision the decision should be realized and if/when it should be re-visited. Links to other decisions and resources might appear here as well.}
