

## Requirement Engineering

It is the systematic process of defining, documenting, and maintaining software system requirements 

![alt text](image-3.png)


## 1. Inception Task

*  A basic understanding of the problem
*   Identify the stakeholders
*   Recognize multiple viewpoints
*   Work towards collaboration
*    Break the ice and initiate the communication


## 2. Elicitation Task

It is difficult because:
* Problems of scope
* Problems of understanding
* Problems of volatility

It is accomplished through two activities:

1. __Collaborative requirements gathering :__ The goal is to identify the problem, propose elements of the solution, negotiate and specify a preliminary set of solutions
2. __Quality Function Deployment:__ 
 It identifies three types of requirements:

* __Normal requirements__ - Requirements stated during  meetings with the customer
* __Expected requirements__ - Fundamental requirements that may not be explicitly stated by customers
*  __Exciting requirements__ - Requirements that go beyond the customer's expectations


## 3. Elaboration Task

* It is an analysis modeling task
* Use cases are developed
* The end result includes the functional, informational, and behavioral domains of the problem

## Building the Analysis Model

Elements of the analysis model:

* __Scenario-based elements__ - Functional, Use Case
* __Class-based elements__ - Implied by scenarios
* __Behavioral elements__ - State diagram
* __Flow-oriented elements__ - Data flow diagram


## 4. Negotiation Task

* Requirements are __prioritized__ by the customers, users, and other stakeholders
* Risks associated with each requirement are identified and analyzed


## 5. Specification Task

* It is the __final work product__ produced by the requirements engineer
*  It formalizes the informational, functional, and behavioral requirements of the proposed software 


## 6. Validation Task

This process checks if the software documentation is consistent, unambiguous, achievable, testable, necessity etc.



## 7. Requirements Management

* The project team performs a set of activities to identify, control, and track requirements
* A __Requirement Traceability Matrix__ (RTM) is a document that tracks project requirements
* RTM is a comprehensive, dynamic document that tracks evolving project requirements

---

## Software Requirements Specification (SRS)

* It lays out functional and non functional requirements and may include a set of use cases
* The output of requirement engineering is the SRS
* First SRS should be written by the __customer__
* Second, SRS should be written by the __developer__
* Quality characteristics of a good SRS are: Complete, Consistent, Unambiguous,  Modifiable, Relevant, Human-readable etc

---
## Functional Requirements

*  Functional requirements describe __what__ the software should do
*  Example : User Authentication, Search Functionality, Explanation etc
* They are gathered by Interviews, Surveys and Workshops

## Non-functional Requirements

* Non-functional requirements describe __how__ the software performs a task rather than what it should do
*  Example : Performance, Usability, Reliability, Security etc
*  Two main categories: Execution qualities, Evolution qualities
*  They are gathered by Performance Benchmarks, Security Standards and Usability Testing.

---
## Decision Table

* They are __tabular representations__ of the possible combinations of conditions and actions that determine the behavior of a system
* They consist of four quadrants: 
* __Condition stubs__ - variables -  input data, user roles
*  __Condition entries__ - values - yes/no, numeric
* __Action stubs__ -  outcomes - updating a database, sending an email
* __Action entries__ -  indicators - X, O, or blank
* Use of Decision Table in Requirements Engineering: Clarifying Business Rules, Handling Complex Decision Logic, Documentation, Test Case Generation


## Decision Tree


* It  is a __graphical representation__ of decision-making
*  It helps visualize  how different conditions lead to specific outcomes
* Use of Decision Tree in Requirements Engineering: Visualizing Decision Logic, Defining System Behavior, Providing Traceability, Simplifying Complex Decisions