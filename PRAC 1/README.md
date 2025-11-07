# PRAC 1
Alejandro Pérez Bueno
Nov 07, 2025

- [Self-Responsibility Declaration](#self-responsibility-declaration)
- [Question 1](#question-1)
  - [Requirement 1: System
    Availability](#requirement-1-system-availability)
  - [Requirement 2: Platform
    Accessibility](#requirement-2-platform-accessibility)
  - [Requirement 3: Data Accuracy](#requirement-3-data-accuracy)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)
  - [Use Case: Analyze Environmental
    Alert](#use-case-analyze-environmental-alert)
- [Question 5](#question-5)
  - [a) Use Cases implicitly stated in the
    interviews](#a-use-cases-implicitly-stated-in-the-interviews)
  - [b) Proposed Use Cases](#b-proposed-use-cases)
  - [c) Task-Level Use Cases for Selected
    Scenarios](#c-task-level-use-cases-for-selected-scenarios)
- [Question 6](#question-6)
  - [a) Functional Requirements as User
    Stories](#a-functional-requirements-as-user-stories)
  - [b) Acceptance Tests for the Example User
    Story](#b-acceptance-tests-for-the-example-user-story)



## Self-Responsibility Declaration

> I certify that I have completed Practice 1 entirely on my own and
> solely with the assistance deemed appropriate by the course
> instructors, according to the guidelines explained in the ‘Originality
> in Assessment’ section of the classroom. I understand that
> non-original work and/or the use of generative AI will result in the
> submitted activity not being graded and will automatically receive a
> score of 0.



## Question 1

### Requirement 1: System Availability

- **Literal phrase from the text:** “deployed in the cloud to ensure
  scalability and 99.99% availability, as the platform must produce
  real-time dat”
- **Technical description:** The system’s architecture needs to be
  really robust so it’s up and running 99.99% of the time. That’s a high
  standard, giving us only about 52 minutes of total downtime for the
  whole year. This is especially important for a system handling
  real-time sensor data.
- **Type of requirement:** This is a **Compliance requirement**, since
  it sets a specific, measurable target for availability.
- **Stakeholder who expressed it:** This was specified by Marc Marquez,
  the CTO.

### Requirement 2: Platform Accessibility

- **Literal phrase from the text:** “the platform must comply with EN
  301 549 accessibility standards (mandatory for ICT services in the
  public sector in the EU) and WCAG 2.1 (level AA) from W3C.”
- **Technical description:** We have to build the user interface so that
  people with different disabilities can still use it without problems.
  This means following the WCAG 2.1 guidelines to level “AA,” which
  includes things like providing text alternatives for images, ensuring
  the whole site works with just a keyboard, and using colors with good
  contrast.
- **Type of requirement:** Since the focus is on making the system easy
  and effective for all users, this falls under **Usability and humanity
  requirements**.
- **Stakeholder who expressed it:** Mireia Ferrater, the COO.

### Requirement 3: Data Accuracy

- **Literal phrase from the text:** “According to Anna, we must be able
  to perform these analyses correctly in at least 95% of cases, to
  predict anomalies (pH changes, invasive species)”
- **Technical description:** The AI models analyzing the data and images
  must be at least 95% accurate. In other words, when the system
  identifies a species or flags a problem, its prediction has to be
  correct 19 out of 20 times for it to be considered reliable enough to
  act on.
- **Type of requirement:** This is another **Compliance requirement**,
  as it establishes a clear, measurable performance metric for the
  system’s output.
- **Stakeholder who expressed it:** The CTO, Marc Marquez, brought this
  up, but he was relaying a need originally identified by Anna
  Esplugues, the Scientific Director.

## Question 2

Based on the interviews, here are some actors that would interact with
the Ocean Ecostructures platform:

- **Port Authority**
- **Energy Company**
- **Public Administration**
- **Marine Biologist**
- **Institutional Manager**
- **Technician**
- **Scientist**
- **Environmental Technician**
- **Communications Department**

## Question 3

A primary conflict emerges from the competing visions of the CEO and the
Scientific Director.

On one hand, the CEO, **Ignacio Herrero**, wants the system to be a
truly “autonomous intelligence.” He pictures a “digital guardian” that
can independently take protective action, such as deploying an
ultrasound platform to ward off threats like harmful algae, all without
waiting for a human to give the okay. His focus is on immediate,
automated response to protect the marine environment.

On the other hand, the Scientific Director and biologist, **Anna
Esplugues**, strongly opposes this whem saying that “all alerts and
action suggestions must be sent to a qualified biologist to decide the
course of action.”. She argues that the risk of the AI making a
mistake—a false positive—is too high and could lead to unintended
ecological damage. For her, the AI should be a powerful tool for
analysis and suggestion, but the final decision to act must always come
from a qualified biologist. She insists on mandatory human oversight for
every action the system proposes.

This creates a fundamental deadlock. The system cannot be both fully
autonomous and simultaneously require mandatory human approval for its
actions. The development team is caught between the CEO’s desire for a
self-managing protector and the lead scientist’s demand for a rigorous,
human-centered safety protocol. A decision must be made about which
philosophy will guide the system’s core function.

## Question 4

### Use Case: Analyze Environmental Alert

- **Use Case Identifier:** `UC-ANA-01`

- **Primary Actor:** Marine Biologist

- **Supporting Actors:**

  - AI Analysis Subsystem
  - Sensor Network
  - Ultrasound Platform

- **Level:** User Goal. This covers the biologist’s primary objective of
  investigating and responding to a potential ecosystem threat.

- **Scope:** System. The interaction is contained within the Ocean
  Ecostructures digital platform.

- **Main Success Scenario:**

  1.  The Sensor Network picks up an annomaly, like a sharp drop in pH
      or video footage of a possible invasive species.
  2.  An alert is automatically triggered by the platform.
  3.  The Analysis Subsystem cross-references the relevant sensor and
      camera data, identifies concerning patterns and generates a report
      that suggests a course of action (such as “recommmend activating
      ultrasound deterrent in Sector 4B”).
  4.  The Marine Biologist is notified with a summary of the alert,
      access to the raw data, and the AI’s analysis.
  5.  The biologist logs in to examine the alert, the underlying data,
      and the AI’s recommendation.
  6.  After reviewing the information, the biologist concurs with the
      assessment and the suggested remote intervention.
  7.  The biologist authorizes the action through the platform’s
      interface to activate the Ultrasound Platform.
  8.  The platform transmits the activation command.
  9.  The alert is logged and closed, documenting the entire incident
      from detection to resolution.

- **Alternative Scenarios:**

  - **3a. False Positive Alert:** the biologist reviews the data and
    determines there is no real threat.
    1.  The biologist dismisses the alert.
    2.  The platform asks for an annotation to explain the dismissal
        (for example: “Natural temperature fluctuation for this
        season”).
    3.  This feedback is used to help train the AI model, and the alert
        is closed.
  - **6a. Requires On-Site Intervention:** The situation is too complex
    for a remote fix and needs a person on-site.
    1.  The biologist chooses the “Requires Field Intervention” option.
    2.  The platform records this decision and can notify a field team,
        depending on the system’s setup.
    3.  The alert is re-assigned for on-site action, concluding the
        biologist’s remote analysis.
  - **6b. Biologist Requests Deeper Analysis:** initial information
    isn’t enough for the biologist to make a confident decision.
    1.  The biologist uses the platform’s tools to run a new analysis,
        maybe by comparing the current data to historical records or by
        changing the AI’s parameters to test a different theory.
    2.  The AI Analysis Subsystem performs the requested analysis.
    3.  The platform displays the new findings for the biologist.
    4.  With the new results, the process continues from step 5 of the
        main scenario.

## Question 5

### a) Use Cases implicitly stated in the interviews

I’ve identified two primary goals that users would want to accomplish
with the platform.

1.  **Activate an Ultrasound Platform:** Based on Anna Esplugues’s
    comments, a key feature would be for a **Marine Biologist** to
    remotely trigger an ultrasound device at a specific installation.
    The idea is that they could respond to a detected threat, like a
    harmful alge bloom, and protect the local ecosystem without needing
    to be physically present.

2.  **Download a Communications Infographic:** Following Lucía Becerra’s
    idea, a staff member from a client’s **Communications Department**
    would need to generate and download a ready-made infographic. This
    would let them easily create visual assets for a municipal website
    or public report to showcase the project’s positive environmental
    impact.

### b) Proposed Use Cases

Here are two additional use cases that would be useful\>

1.  **Configure a New Client Project:** From a system management
    perspective, an internal **System Administrator** must be able to
    set up a new project for a client. This is a prerequisite for
    anything else. The process would involve defining the project’s
    geographic boundaries on a map, associating specific sensor and
    hardware IDs with that project, and creating the initial admin
    account for the client’s own team.

2.  **Validate AI Species Identification:** To achieve the 95% accuracy
    goal mentioned by Marc Marquez, the AI models will require ongoing
    training and supervision. This means a **Marine Biologist** would
    need a way to validate the AI’s findings. The platform could present
    the biologist with images where the AI’s confidence is low. The
    biologist would then confirm or correct the species tag, which in
    turn helps the model learn and improve its performance over time.

### c) Task-Level Use Cases for Selected Scenarios

Let’s break down two of the broader use cases into the smaller and more
granular steps that a user would take to accomplish the,.

\*\*1. `Download a Communications Infographic` use case:

To generate a report, a communications staffer would likely perform
these smaller tasks:

- **Select an Infographic Template:** First, the user would be presented
  with several visual styles or layouts (“Annual Summary,” “Species
  Spotlight”) and would choose the one that best fits their needs.
- **Choose a Time Period for the Data:** Next, they would need to select
  a start and end date. This defines the data range that will populate
  the infographic, such as “the last quarter” or a specific calendar
  year.

\*\*2. `Configure a New Client Project` use case

Similarly, the administrator’s workflow for setting up a project would
involve steps like these:

- **Add a User Account to a Project:** Inside the project configuration
  area, the admin would use a form to enter a new user’s details (name,
  email, role) to grant them access to that specific client’s project.
- **Link a Sensor to an Installation:** The admin would also need to
  select some specific installation within the project and enter the
  unique ID of a physical sensor to associate its incoming data stream
  with that location.

## Question 6

### a) Functional Requirements as User Stories

Based on the interviews, I’ve identified several key functional needs
and written them as user stories:

- The interviews stated that “Each client—whether a port, an energy
  company, or a public administration—must be able to access their
  digital space, view the status of their installations, consult
  reports, and receive alerts” This can be expressed as a user story for
  the client:
  - As a **client**, I want to access my personal digital space so that
    I can monitor the status of my installations, review reports, and
    manage alerts.
- Another requirement was for marine biologists to “interact remotely
  with the ecosystem, such as activating ultrasound platforms to protect
  certain areas” As a user story, this would be:
  - As a **marine biologist**, I want to be able to remotely activate
    the ultrasound platforms so that I can proactively protect the
    ecosystem from identified threats.
- For public administration, the need to “download consolidated reports
  from several installations and use them as evidence in a European
  audit process” leads to this story:
  - As a **public administration staff member**, I want to download
    consolidated reports from multiple installations so that I can use
    the data as official evidence for sustainability audits.
- Finally, the communications team needs to “download an infographic
  ready to share on the municipal website” The corresponding user story
  is:
  - As a member of a **communications department**, I want to download
    ready-to-use infographics about the project’s impact so that I can
    easily share positive results with the public.

### b) Acceptance Tests for the Example User Story

Looking at the user story: *“As an environmental technician I want the
platform to automatically generate an annual environmental impact report
so that I can evaluate the evolution of biodiversity in the port,”* here
are three acceptance tests to make sure it’s working correctly.

1.  **The report must compare the project area to a control area.** When
    the technician generates the report, it should automatically include
    a section contrasting the biodiversity metrics (like species count)
    of the regenerated zone with data from a designated, non-intervened
    area for the same time frame.

2.  **The system should handle incomplete data gracefully.** If a
    technician requests a report for a new installation that has only
    been active for six months, the platform should generate the report
    covering that specific period and clearly state the time frame,
    rather than failing or showing blank data.

3.  **The final report needs to have clear data visualizations.** It
    must feature at least one graph or table showing how the main
    biodiversity indicators have evolved month-over-month, allowing the
    technician to easily spot trends at a glance.
