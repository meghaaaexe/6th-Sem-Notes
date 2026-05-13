# Software Engineering - 22AIE311

## Software’s Dual Role

1. __Software is a product__

* Delivers computing potential
* Produces, manages, acquires, modifies, displays and transmits information

2. __Software is a vehicle for delivering a product__

* Supports or directly provides system functionality
* Controls other programs (e.g., an operating system)
* Effects communications (e.g., networking software)
* Helps build other software (e.g., software tools)

##  Bathtub Curve

![alt text](image.png)

Bathtub Curve is a graph that is used to graphically demonstrate run-to-failure maintenance strategy.This curve represents overall life cycle of assets and failure rate of overall population of assets over time. Bathtub curve is  divided into three different sections:

1. __Infant Mortality Section :__ In this section, asset is beginning with its usage for first time. Initially, failure rate is very high and with increasing time, there is a gradual decrease in failure rate. Failures are usually occurred due to manufacturing defects, installation issues, design issues, material defects, etc. 
2. __Normal Life Section :__ This section represents normal operating life of assets.In this section, asset is still experiencing failure but at normal and low rate. Failures are usually occurred due to overloading, hidden defects, collision with other objects, mistakes of personnel, etc. 
3. __Wear-out Section :__ In this section, there is gradual increase in failure rate of assets with increasing time. Failures are usually occurred due to fatigue, wear, gradual deterioration, corrosion, etc. This period represents end of life cycle of assets.

## Hardware vs Software

![alt text](image-1.png)

## Legacy Software

* The older programs which are developed decades ago that are still in use by performing modifications in order to meet the business requirements. 
* Many legacy systems remain supportive to core business functions and are important to  business. Hence, legacy software is characterized by longevity and business criticality. 

## Software as a Layered Technology

![alt text](image-2.png)

* Any engineering approach must rest on an organizational commitment to __quality__
* __Process__ is the glue that holds the technology layers together & enables timely development of computer software. It forms the basis for management control of software projects 
* __Methods__ encompass a broad array of tasks that include communication,requirements analysis, design modeling, program construction,testing support
* __Tools__ provide automated or semi-automated support for the process and methods

## SDLC Models

![alt text](image-4.png)

![alt text](image-6.png)

## Traditional vs Agile

![alt text](image-7.png)

## Agile Scrum Methodology

* __Product owner:__ Creates an estimated wish list that is  identified as a __product backlog__.
* __Product Backlog__ is a list of new features, enhancements, bug  fixes, tasks, or work requirements needed to build a product.

* __Scrum team:__ It takes one little part of the top wish list,  termed as __Sprint Backlog__ and work out in order to implement it.
* __Sprint Backlog__ is a set of product backlog tasks that have been  promoted to be developed during the next product increment. 
* __Product Increment__ is the customer deliverables that were produced  by completing product backlog tasks during a sprint. 
* Scrum team concludes their __sprint__ backlog task  in a Sprint, i.e., a period of 2-4 weeks
* The progress of their work can be accessed through a  meeting that is called __Daily Scrum__.
* The __Scrum Master__ maintains the team focused towardtheir targets

![alt text](image-15.png)

---

## Requirement Engineering

It is the systematic process of defining, documenting, and maintaining software system requirements. It builds a bridge from the system requirements into software design and construction

![alt text](image-3.png)


## 1. Inception Task

*  A basic understanding of the problem
*   Identify the stakeholders
*   Recognize multiple viewpoints
*   Work towards collaboration
*    Break the ice and initiate the communication


## 2. Elicitation Task

It is difficult because of problems of scope, understanding and volatility

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
  
 https://www.geeksforgeeks.org/system-design/use-case-diagram/


## Building the Analysis Model


* An analysismodel in software engineering is created to define the functional, behavioral, and datarequirements of a system.
* It acts as a bridge between system description and design.

![alt text](image-10.png){width=100% height=50%}

Elements of the analysis model:

* __Scenario-based elements__ - Functional, Use Case
* __Class-based elements__ - Implied by scenarios
* __Behavioral elements__ - State diagram
* __Flow-oriented elements__ - Data flow diagram

https://www.geeksforgeeks.org/system-designunified-modeling-language-uml-class-diagrams/


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
* RTM is a comprehensive, dynamic document that tracks evolving project requirements.
* It  ensures the final product aligns with initial user expectations.

RTM is of 3 types:

1. __Forward traceability:__ 
Objective: to ensure every requirement is tested and properly implemented.
Direction: from requirements to test cases/deliverables

2. __Backward traceability /  Reverse Traceability:__ 
Objective: to ensure no unnecessary features are added and to verify alignment with initial requirements.
Direction: from test cases / deliverables to requirements.

3. __Bidirectional traceability:__
Objective: to ensure complete alignment between requirements and test cases, supporting thorough verification and impact analysis.
Direction: from / to requirements and from / to test cases / deliverables.

---

## Software Requirements Specification (SRS)

* It lays out functional and non functional requirements and may include a set of use cases
* The output of requirement engineering is the SRS
* First SRS should be written by the __customer__
* Second, SRS should be written by the __developer__
* Quality characteristics of a good SRS are: Complete, Consistent, Unambiguous,  Modifiable, Relevant, Human-readable etc


## Functional Requirements

*  Functional requirements describe __what__ the software should do
*  Example : User Authentication, Search Functionality, Explanation etc
* They are gathered by Interviews, Surveys and Workshops

## Non-functional Requirements

* Non-functional requirements describe __how__ the software performs a task rather than what it should do
*  Example : Performance, Usability, Reliability, Security etc
*  Two main categories: __Execution qualities__ -  security and usability, which are observable at run time, __Evolution qualities__ - testability, maintainability, and scalability that are present in the static structure of the software system.
*  They are gathered by Performance Benchmarks, Security Standards and Usability Testing.

![alt text](image-8.png)

---
## Decision Table

* They are __tabular representations__ of the possible combinations of conditions and actions that determine the behavior of a system
* They consist of four quadrants: 
* __Condition stubs__ - variables -  input data, user roles
*  __Condition entries__ - values - yes/no, numeric
* __Action stubs__ -  outcomes - updating a database, sending an email
* __Action entries__ -  indicators - X, O, or blank
* Use of Decision Table in Requirements Engineering: Clarifying Business Rules, Handling Complex Decision Logic, Documentation, Test Case Generation
* They are helpful in testing, development process,  prepare requirements etc
![alt text](image-9.png)

## Decision Tree


* It  is a __graphical representation__ of decision-making
*  It helps visualize  how different conditions lead to specific outcomes
* Use of Decision Tree in Requirements Engineering: Visualizing Decision Logic, Defining System Behavior, Providing Traceability, Simplifying Complex Decisions
  
---

## Requirements Analysis

* It specifies software’s operational characteristics, indicates software's interface and establishes constraints that software must meet
* Requirements analysis allows the software engineer (analyst) to :
  * __elaborate__ on basic requirements established during earlier 
requirement engineering tasks
  * __build models__ that depict user scenarios, functional activities and
problem classes 

---
# Design Engineering
## Software Design Process

![alt text](image-11.png)

__McGlaughlin’s__ 3 characteristics (goals) as a guide for the evaluation of a good design are as follows:

1. __Implement All Requirements:__ The design must meet all explicit and implicit stakeholder requirements.
2. __Ensure Readability:__ The design must be easily understood by developers, testers, and maintainers.
3. __Provide a Complete Picture:__ The design should fully address the data, functional, and behavioral aspects of the system. 

__HP’s__ set of software quality attributes as acronym __FURPS__

1. __Functionality:__ Refers to the feature set, capabilities, and security of the application.
2. __Usability:__ Focuses on human factors, aesthetics, consistency in the user interface, online help, and documentation.
3. __Reliability:__ Covers the frequency of failure, recoverability, predictability, accuracy, and mean time between failures (MTBF).
4. __Performance:__ Measures the software’s efficiency in terms of speed, response time, resource consumption, throughput, and scalability.
5. __Supportability:__ Encompasses testability, maintainability, serviceability, flexibility, installability, and localizability. 

## Design Concepts

“The beginning of wisdom for a [software engineer] is  to recognize the difference between getting a program to work, and getting it right.” ~ M. A. Jackson

1. __Abstraction :__ Abstraction simply means to hide the details to reduce complexity and increase efficiency or quality. __Procedural abstraction__ refers to a sequence of instructions that have a specific and limited function. __Data abstraction__ a named collection of data that describes a data object.
2. __Modularity:__ It means dividing the system or project into smaller parts to reduce the complexity of the system or project. Modularity in design means subdividing a system into smaller parts so that these parts can be created independently and then use these parts in different systems to perform different functions.
3. __Architecture :__ It is a concept that focuses on various elements and the data of the structure. These components interact with each other and use the data of the structure in architecture.
4. __Refinement:__ It is a  concept of software design is a process of developing or presenting the software or system in a detailed manner which means elaborating a system or software.
5. __Refactoring:__ It means reconstructing the design to reduce complexity and simplify it without impacting the behavior or its functions.
6. __Pattern:__ It means the repetition of a solution to a common 
recurring problem within a certain context.
7. __Coupling:__ It refers to the degree of interdependence between software modules. High coupling means that modules are closely connected and changes in one module may affect other modules. Low coupling means that modules are independent.
8. __Cohesion:__ It refers to the degree to which elements within a module work together to fulfill a single, well-defined purpose. 
 
## Types of Coupling

![alt text](image-12.png)

1. __Data Coupling:__ Modules communicate by passing only data information
2. __Stamp Coupling:__  A whole data structure is passed, but only part is used
3. __Control Coupling:__ Modules communicate by passing control information
4. __External Coupling:__  The modules depend on other modules or external to the software being developed.
5. __Common Coupling:__ The modules have shared data such as global data structures.
6. __Content Coupling:__ In a content coupling, one module can modify the data of another module, or control flow is passed from one module to the other module.
   
## Types of Cohesion

![alt text](image-13.png)

1. __Coincidental Cohesio:__ Unrelated functions are grouped together randomly.
2. __Logical Cohesion:__ Related by category, but selected using a control flag.
3. __Temporal Cohesion:__ Tasks executed at the same time.
4. __Procedural Cohesion:__ Elements are related and must follow a specific order.
5. __Communicational Cohesion:__ Functions operate on the same data.
6. __Sequential Cohesion:__ Output of one function becomes input to next.
7. __Functional Cohesion:__ Module performs exactly one well-defined task.


In conclusion, it’s good for software to have low coupling and 
high cohesion. 

---

## Epics, User Stories and Story Points

* __Epics__ provide the big-picture vision, representing significant functionality or features.
* __User stories__ break epics down into specific, actionable tasks.
* __Story points__ offer a way to measure effort, helping teams estimate and manage their workloads 
  
## User Stories

A User Story is a requirement expressed from the perspective of an end-user goal. It is a well-expressed requirement.

The 3C’s of User Stories:

1.__Card:__ 

* The Front of the Card: A unique “Story Identifier”, usually a number or reference
* The Back of the Card: Acceptance criteria 
2. __Conversation__
3. __Confirmation__

## Estimate story points in Scrum

Scrum story points are usually represented using the Fibonacci sequence - 1, 2, 3, 5, 8, 13, 20, 40, and 100

Create a matrix to visualize story point values. Make a row for each number in the Fibonacci sequence.

![alt text](image-14.png)

## Backlog Grooming

Makeyourproduct backlog __DEEP__

1. __Detailed Appropriately:__ Top items have more detail, clear acceptance criteria, and are ready for development. Lower-priority items are less detailed.
2. __Estimated:__ Items are sized to allow for velocity forecasting.
3. __Emergent:__ The backlog is a living document, updated continuously as new information and user feedback.
4. __Prioritized:__ The backlog is ordered with the most valuable, high-impact, or risk-reducing items at the top.

---

## Extreme Programming(XP)

* Extreme Programming (XP) is an Agile software development methodology that focuses on delivering high-quality software through frequent and continuous feedback, collaboration, and adaptation.
* XP is based on the four simple values:
    * Uniformity
    * Simplicity
    * Communication
    * Feedback and Endurance
* XP is the most suitable for:
    * Small and medium size projects
    * New technologies
    * Projects with unclear requirements
    * Risky projects
* __Pair programming__ is a software development practice where two programmers work together on one computer.
* The __driver__, writing code while the other, the __observer or navigator__, reviews each line of code as it's typed. 
* This real-time collaboration helps catch errors early, improves code quality

---
  