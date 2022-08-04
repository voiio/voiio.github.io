# Team Structure

## Org Chart & Interfaces

```mermaid
flowchart TD
    CEO{CEO};
    CTO{CTO};
    PO{Product Owner};
    team{voiio Team};
    TM{Project Lead};
    TL{Dep. Head};
    CEO -- compnay OKR --> CTO;
    CTO -- product OKR --> PO;
    CTO <-. platform architecture .-> TM;
    PO -- project OKR --> TM;
    TM <-- project collab. --> TL;
    PO <-- roadmap planing --> TL;
    PO -- product update --> team;
```

## Artifacts & Ownership

```mermaid
flowchart LR
    CEO{CEO};
    CTO{CTO};
    PO{PO};
    TM{PL};
    companyVision[[Company Vision]];
    productVision[[Product Vision]];
    productRoadmap[[Product Roadmap]];
    companyObjectives[[Company Objectives]];
    companyKeyResults[[Company Key Results]];
    productObjectives[[Product Objectives]];
    productKeyResults[[Product Key Results]];
    projectKeyResults[[Project Key Results]];
    projectObjectives[[Project Objectives]];
    project[[Project]];
    CEO -. owns .- companyVision;
    CEO -. sets .- companyObjectives;
    CTO -. delivers .- companyKeyResults;
    CTO -. owns .- productVision;
    CTO -. set .- productObjectives;
    PO -. delivers .- productKeyResults;
    PO -. owns .- productRoadmap;
    PO -. sets .- projectObjectives;
    TM -. delivers .- projectKeyResults;
    TM -. owns .- project;
```

### Visions

A clear vision needs to be set for the company and all departments. Those documents
need to be shared with all employees.

### OKR

_ORK = Objective Key Result_

We use OKRs as a bidirectional communication, with goal alignment in the form of
objectives and impactful delivery in form of key results. They must be agreed upon
by both the team and manager.

ORKs are communicated within the company to identify synergies or conflicts of interest.

#### Objectives

Objectives are set by the manager in alignment with the company or product vision.
They are their main tool of control and need to be highly specific and achievable.
Furthermore, they should be outcome and not output oriented. Meaning that they should
define a goal, not implementation or specific features.
Objectives may change over time, to allow the manager to set the focus on new challenges.

#### Key Results

Key results are committed outcome towards the objective set by the manager.
They must be achievable by the team without external dependencies or side effects.
Should a team struggle to define key results, this might indicate that the manager
needs to set a more refined objective.

### Product Roadmap

The product roadmap help organize and communicate individual product ORKs for the
upcoming month. The document is owned and maintained by the product owner.

The product owner does not define a timeline based on estimates or solutions, but based
on amount of time they want to invest to achieve an objective.

The product owner must frequently update and align the roadmap with relevant stakeholders.

### Project

The project is owned by a project lead. Any engineer can be the project leads.
They are responsible for the project's outcome. They gather requirements, define
solution, and coordinate the team. The team usually consists of other engineers.

They product manager must frequently update and align the project with relevant stakeholders.
