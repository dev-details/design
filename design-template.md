
# Design Template

This is a design document. We want a lightweight and [autonomous design process](https://blog.devdetails.com/p/autonomy-for-software-architecture). We want "just enough" information for stakeholders to move forward.

## About the template

### When should the Design Doc Template be used?

- When the problem is unclear.
- When the requirements are unclear.
- When multiple teams are impacted (they need to produce or consume APIs).
- When multiple teams will implement.
- When the scope or risk is high (one-way vs a two-way door).

### When is a design document too much?

- When the task is small, only one team is impacted by the change.
- Even then, the same principles of design apply, you might not need a dedicated document to represent it. Capture the information in the story.

### How much design is enough?

- When the functional and non-functional requirements are clear.
- When everyone is aligned.
- When you have enough information that all parties say, "we're good to go".
- For more risk, or two-way doors, more design is needed.

### Keep design documents focused.

- If a design is too big (has too much information, too many diagrams, too much scope), it should be broken into several design documents.

  - **Visionary** – Long term technical vision.
  - **Strategic** – High-level direction setting for many tactical designs.
  - **Tactical** – A design for a specific problem (a typical design document).

- Design documents should not contain deep-dive research material – only the outcome. Example of research materials include comparison charts, existing API specifications, low-level diagrams, details about considered alternatives, etc. You can add additional materials as sub-pages to the design.

### How to use this template

These blocks are hints and guides. Do not leave them in the design document. Once you fill in a section, delete the hints and guides.

The section headings below are meant to drive conversation and consideration. What sections are important for your team to reflect on for each design? Each section is not mandatory. Add or remove sections as you see fit based on the scope and complexity of the design. Something with smaller scope and complexity should have fewer sections. Only leave in sections that have relevant information.

### Design Document Ground Rules

- Prefer text bullets over paragraphs.
- Prefer diagrams over description. Prefer text-to-diagram solutions over drag-and-drop.
- Prefer links over repeating information. This will create a graph of backlinks.
- Rather than ask questions, make assumptions. It is better to put something that is wrong on paper to discuss than it is to ask open ended questions.
- Document assumptions _as_ assumptions, get alignment from stakeholders, restate as declarations.
- Use a live-document format that supports inline comments, editing without friction, and judicious links.
- Call out patterns (architecture, software, etc.). They are a shorthand for understanding.

### DACI

The best way to scale architecture processes is with [autonomy](https://blog.devdetails.com/p/autonomy-for-software-architecture). To achieve autonomy, everyone must have clear expectations of everyone's role. [DACI](https://blog.devdetails.com/p/adopting-daci) works well for clarifying roles for the design process. Design needs a clear Driver to own the process.

Use this section to define who will be involved in this design.

- **Driver**: If you’re creating this design, you’re the Driver. A single Senior/Staff+/Principal Engineer drives the design and is responsible for running the decision-making process. This person will endeavor to understand the project and facilitate stakeholder communication.
- **Approver**: The goal is to minimize approval needed while eliminating bottlenecks. So the same person can't be the approver for everything. We want to ask 1 or 2 people "we good to go?" and get a quick answer. It's those 1 or 2 peoples' responsibility to ensure things are in order and indeed good-to-go.
- **Contributors**: This list can get large and unwieldy and may include Architects, Product Managers, UX Designers, Security, Data Engineers, Customer Support, QA, etc. To determine who should be involved, use [Andrew Harmel-Law's Advice Process](https://martinfowler.com/articles/scaling-architecture-conversationally.html#TheMostFundamentalElementDecision-makingViaThex201cadviceProcessx201d): consult people with expertise in the area and everyone meaningfully affected.
- **Informed**: Inform anyone meaningfully impacted. The Larger the project, the larger the impact.

## Situation

### Context

[Context is more important than the solution](https://blog.devdetails.com/p/design-context-is-more-important). This is a live document so update it as you learn more information and keep it concise. The goal is to understand the problem so that the team can pivot as much as needed to deliver a solution. Leave the details for [as late as responsible](https://blog.codinghorror.com/the-last-responsible-moment/).

The first paragraph of **Context** is what the reader needs to understand before being told the problem.

- Use plain language.
- Keep it simple.
- Remove any unnecessary words.

Put what the reader needs to understand before being told the problem.

### Problem

Diagrams explain a lot more than words alone. For the Problem, it is helpful to diagram at the C1 System Level or C2 Component Level to help answer:

- Who is using the system?
- How are they using it?
- What components are interacting?
- Level 1 or 2 [C4 Model](https://c4model.com/) diagram

What problem are we trying to solve? This should be oriented around the customer's need.

### Purpose


The **Purpose** explains the benefit this solution will provides to the business. It represents the 'why' of a project by articulating the objectives or problems a business aims to address. These might be strategic goals, like expanding into a new market, operational goals, like improving efficiency, or customer-focused goals, like enhancing user experience.

Business impact is the most crucial consideration of a design. If it does not satisfy the needs of the business, what is the point? For small projects, you can interweave the **Purpose** into **Context** above and remove this heading.

You may find it useful to use the **Goals** and **Non-Goals** sub-sections of **Purpose** to break it down.

Describe the Purpose from a business perspective.

#### Goals

- Bullet point high-level goals that drive the solution.

#### Non-Goals

- Bullet point high-level goals we should avoid getting distracted with.

## Expectations

After we understand the problem, we need to understand what requirements and constraints drive the solution.

As the text below explains, requirements use key words from [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt) to indicate the significance of a particular requirement. These key words MUST be used when describing requirements. Keep the following text in the final design document to inform readers of their meaning.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

### Use Cases

Use Cases help identify, define, and organize requirements. Each Use Case represents a function or a goal a user can achieve using the system.

They typically follow the template: “{actor} wants to {action}, so that {outcome}". The “outcome” is essential to understand the reason a user wants to perform an action so we can design a solution to fit their needs.

Use Cases are written from the user’s perspective. If this is a customer facing feature, the user is typically an end-user customer. If this is an internal API, the user is often a client such as a mobile device or desktop application. The “actor” is the role the user portrays (ex: User, Developer, iOS App, Sales Agent).

- {actor} wants to {action}, so that {outcome}

### Functional Requirements


Functional requirements represent the 'how' -- how we will solve the customer problem -- not the implementation details. They lay out in detail the functionality that a system, application, or product must have to meet the identified business needs. They describe the features a system must possess and inform how the solution will solve the problem.

Describe what a system should do. For example, an e-commerce website should be able to display product details when a user clicks on a product.

If you're not sure where to start, look at the Use Cases. Multiple requirements can be derived from a single Use Case. Make informed assumptions and write them as requirements with indication that they are assumptions with “ASSUMPTION”. Confirm your assumptions with stakeholders, refine as needed, and remove the ASSUMPTION indication.

- You SHOULD describe a functional requirement

### Non-functional Requirements


Non-functional requirements, as opposed to functional requirements, specify criteria that can be used to judge the quality of operation of a system, rather than specific behaviors. They are also known as "qualities" of the system. Non-functional requirements are crucial to the success of software and systems because they control attributes such as reliability, performance, security, portability, and usability.

Describe how a system performs a certain function. For example, "the e-commerce website must be able to load the product details within two seconds 95% of the time".

Do back of the napkin math. How many daily users? How many requests per second? How much data will that create? How long will that data be retained? How much up-time is required?

Most non-functional requirements should be quantified. "Must be real-time" is not a quantified. How fast is "real-time"? For some applications, 15 minutes is fast enough. For others, responses must happen within 200 milliseconds. Be precise, but be practical.

These non-requirements inform how robust the solution need be to solve the problem. This is important for right-sizing the solution. For example, if the solution only needs to support 10 users, then it can be much simpler than a solution that must support 1000 users.

If you're not sure where to start, make informed assumptions and write them as requirements with indication that they are assumptions with “ASSUMPTION”. Confirm your assumptions with stakeholders, refine as needed, and remove the ASSUMPTION indication.

- You SHOULD describe a non-functional requirement within 5 minutes 95% of the time

### Constraints

Requirements are generally open to interpretation when designing a solution, whereas constraints are fixed factors that must be adhered to.

Constraints restrict design freedom. These are specific requirements that limit what can be done. Only list constraints that truly constrain the solution.

For example:

- Must use existing infrastructure
- Must be implemented in Golang
- Must support Windows 10 through 11

- You MUST list constraints as MUSTs

### Exclusions


Things we are explicitly not doing. It is just important to call out what we're not doing as to call out what we are. If we've explicitly decided not to do something, record what that is and why. 

This will prevent us from creating a solution for problems we don't have or problems we're not concerned about. It will help achieve a simpler solution and it aligns everyone on what we've decided is out of scope.

- This design does not cover feature XYZ, that will be handled by PROJ-1234

## Direction

This section explains what direction to take to solve the identified problem.

### Solution
 
Describe the proposed solution. Favor diagram (PlantUML/C4) over text.

The amount of context you need to provide is proportional to the complexity and impact of the solution.

For this part of the Solution, diagram at the C1 System Level or C2 Component Level to help answer:

- Who will use the system?
- How are will they use it?
- What components will interact?

### Implementation Details

Provide the details of how the solution will be implemented. This could include information about specific technologies, atypical algorithms, architecture diagrams, or code snippets. Avoid going too deep into low-level specifics.

For the Implementation Details, diagram at the C2 Component Level, C3 Container Level, or C4 Code Level.

- {detail 1}

### {Topic}
 
If the solution has different components or aspects, consider breaking them down into subtopics. 

  
- {detail 1}

### Data Model

This section describes the data structures, or the database schema used in the solution. This could be presented in the form of diagrams, tables, or descriptive text. The goal is to give a clear idea of how data is organized, stored, and accessed.

Add sub-sections as needed.

For the Data Model, use a [Class Diagram](https://plantuml.com/class-diagram) or [Object Diagram](https://plantuml.com/object-diagram).

### Deployment

Describe how the system will be deployed, including the environments (development, testing, production), the process, and any tools or technologies used. You may also wish to cover any prerequisites, dependencies, or steps to verify successful deployment.

For the Deployment, use a [Deployment Diagram](https://plantuml.com/deployment-diagram).

### Observability

Non-functional requirements describe the required uptime, performance, etc. Observability is how we measure that we are meeting those non-functional requirements.

#### Metrics

Measure how the system is performing. What are the _failure_
and _success_ conditions.

#### Logging

Are there any special considerations for logging? Will particular messages be logged or queries that will help with debugging, customer support, etc?

#### Alerts

How will you know the system is behaving outside normal parameters. What are the SLOs?

Consider business case metrics. These are often indicators of a business problem before they are a technical problem.

For example, deviation from normal sales volume may indicate that there is a critical problem that is not being triggered by performance metrics.

### Infrastructure

Outline any infrastructure changes that will need to be implemented for the new solution. This could include hardware, networks, servers, or third-party services.

### Privacy and Security

Discuss the privacy and security implications of the system, such as encryption, access controls, data anonymization, and compliance with relevant regulations. Be sure to address any potential threats and how they will be mitigated.

### API

Provide a detailed overview of the application's API, including each endpoint, its purpose, the HTTP methods it supports, the data it accepts, and the data it returns.

A specification format (OpenAPI, AsyncAPI, JSON Schema) should be used to document the API. Instead of putting in the design document, you can link to a repository or pull request for this. At the very least, this could be represented as a table or a list, and may include example requests and responses.

### Impact

Is there a meaningful impact of this change on the system? Who is affected (business, customers, or other teams)? This may include benefits such as improved efficiency, cost savings, increased customer satisfaction, or other key metrics. Also consider potential negative impacts, such as disruption to existing processes, and how these will be mitigated.

### Alternatives Considered

Were alternative implementations considered? Why were they ultimately not used? Anticipate "Did you consider...?" questions and answer them here.

This should be a bulleted list with short descriptions of the solution and why it was not used. If there was more documentation created, link to it.

### Risks and Mitigations

Every project carries some risk. Identifying what could go wrong and how it will be addressed is crucial to any design document. Potential risks could be technical, operational, organizational, or related to the market or product.

#### Technical Debt

Technical Debt should be taken on with eyes wide open. It's a conscious decision to do take a short cut. Why are we taking that short cut? What debt are we incurring?

Record Technical Debt so we understand the risk we are assuming and the cost (with interest) that we're going to pay to address.

### Milestones

The goal is not to plan the work in the design. However, it is sometimes useful to recommend how large projects can be logically split apart. Earlier milestones have more detail. The details get more nebulous the further out the milestone.

### Conventions

This section is for conventions used for this implementation. Style guide, best practices, etc. If your team already has standard conventions in place, no need to reiterate them here.

## Appendix

### Questions and Concerns

Anticipate questions. Answer them in the rest of the design.

For explicit questions, list them here, along with their answer. Then incorporate the answer into the design.

If the answer is not know, put a todo. All todos should be resolved before moving forward with the design.

### Glossary

Define domain-specific terminology that's necessary to understand this document. It helps in improving the clarity of the document and ensures all readers are on the same page. If someone asks, “What does that mean?”, you need to define it.

It is best to make links of unclear terms that link to confluence pages that define the terms. We should re-use existing definitions instead of repeating them in every design doc.

