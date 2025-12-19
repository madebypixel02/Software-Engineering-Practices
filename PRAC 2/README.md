# PRAC 2
Alejandro Pérez Bueno
Dec 19, 2025

- [Self-Responsibility Declaration](#self-responsibility-declaration)
- [Question 1](#question-1)
- [Question 2](#question-2)
  - [Use cases](#use-cases)
  - [Use case diagram](#use-case-diagram)
- [Question 3](#question-3)
  - [Class diagram](#class-diagram)
  - [Keys, constraints and derived
    information](#keys-constraints-and-derived-information)
- [Question 4](#question-4)
  - [Class Diagram](#class-diagram-1)
  - [Keys, constraints and derived
    information](#keys-constraints-and-derived-information-1)
- [Question 5](#question-5)
  - [Class Diagram](#class-diagram-2)
  - [Keys, constraints and derived
    information](#keys-constraints-and-derived-information-2)



## Self-Responsibility Declaration

> I certify that I have carried out Practice 2 completely individually
> and only with the help that the teaching staff of this subject
> considers appropriate, according to the instructions explained in the
> “Originality in the evaluation” section of the classroom. I understand
> that non-original work and/or the use of generative AI will mean that
> the submitted activity will not be corrected and will automatically be
> assigned a grade of 0.



## Question 1

Here is a Swimlane activity diagram based on the success and alternate
scenarios.

![](README_files/mediabag/8392e76d1563bf30c9d6d8ac5a108d44d7941d5b.svg)

## Question 2

### Use cases

Old ones:

1.  As a port technician, I want to consult reports to know the status
    of marine space indicators.
2.  As a marine biologist, I want to monitor the marine environment to
    detect changes in the ecosystem and adjust regeneration strategies
    to ensure its health.
3.  As public administration staff, I want to visualize on a map the
    effectiveness of interventions in various ports to efficiently
    allocate available funds.
4.  As a communications technician, I want to download infographics to
    clearly show citizens the improvement in biodiversity.

New ones:

5.  As a port technician, I want to register maintenance incidents for
    marine sensors.
6.  As a marine biologist, I want to compare current water quality data
    with historical data.
7.  As public administration Staff, I want to approve budget allocations
    for specific port interventions.
8.  As a communications technician, I want to publish an annual
    biodiversity newsletter for the public web portal.

### Use case diagram

![](README_files/mediabag/8c4b54fe025b5725a06b6427ad8963a1499f160d.svg)

## Question 3

### Class diagram

![](README_files/mediabag/f5d338da321b2f51f3373372278f6b2f660a9d87.svg)

### Keys, constraints and derived information

#### Keys of the domain classes

These attributes act as unique identifiers for each class:

- **Sensor:** `id`
- **Action:** `actionID`
- **Biologist:** `employeeID`
- **Algorithm:** `name`: Since the system will store the name to
  identify the algorithm that processes data, it functions as the unique
  key here.

#### Integrity Constraints

- **Record Specialization:** Every `Record` has to be specifically a
  `PhysicalRecord` or `BiologicalRecord`. No plain generic records
  allowed, so `Record` works as an abstract class.
- **Dismissal Reason Validity:** The `dismissalReason` is limited to
  just “not relevant” or “false positive” which may be expressed as an
  enumeration.
- **Dismissal Logic:** You only store a `dismissalReason` when the alert
  is actually dismissed.
- **Alert Management:** Each `Alert` gets handled by just one
  `Biologist`, as the description notes that an alert is managed only by
  a single biologist.
- **Action Origin:** An `Action` comes from either an `Algorithm` or a
  `Biologist`, but never from both at the same time (this is a case of
  an exclusive OR).

#### Derived Information

- **Biologist: `/alertsManaged`**: You can get this by simply counting
  how many `Alert` instances are linked to the `Biologist` via the
  “manages” relationship right now.

## Question 4

### Class Diagram

![](README_files/mediabag/dc0f01f3ee9ec5f535b01bf805dd38d87d773ec6.svg)

### Keys, constraints and derived information

#### Keys of the domain classes

These attributes act as unique identifiers for their class:

- **Sensor:** `id`
- **Action:** `actionID`
- **Report:** `reportID`
- **User (Biologist / EnvironmentalTechnician):** `employeeID`
- **Algorithm:** `name`: since algorithms are named uniquely in the
  system.
- **Record:** `Sensor.id` + `timestamp` + `key`. It’s not one single
  field, but the combination of all three do make it unique.

#### Integrity Constraints

- **State Transitions:** Alerts have to go through states in order from
  `New` to `InProgress` to `Resolved`.
- **InProgress Assignment:** Once it’s `InProgress`, it has to be handed
  off to a `Biologist`.
- **Resolution Review:** For `Resolved` alerts, they need a check from
  an `EnvironmentalTechnician` before closing.
- **Report Content:** Reports can only pull in alerts that are already
  `Resolved`.
- **Technician Specialties:** Each `EnvironmentalTechnician` needs 1 to
  3 specialties (thus the \[1..3\] in the diagram).
- **Dismissal Status:** If there’s a `dismissalReason`, the alert isn’t
  active anymore
- **User Uniqueness:** We can’t have two users with the same
  `employeeID` or `email`

#### Derived Information

- **Biologist: `/alertsManaged`**: we can count the `InProgressAlert`
  assigned to that Biologist at a given time.
- **ResolvedAlert: `/duration`**: we can subtract the `dateGenerated`
  from the `resolutionDate` to get how long it took.
- **Report: `/numberOfAlerts`**: we can count the `ResolvedAlert`
  connected to the report through the “includes” link.

## Question 5

### Class Diagram

![](README_files/mediabag/4bce9b857a709488ed20e7a10c42118891edbccc.svg)

> [!NOTE]
>
> The Classes from previous exercies are ommited because they remain the
> same. They all stem from the `EnvironmentalTechnician`

### Keys, constraints and derived information

#### Keys of the domain classes

- **Location:** postalCode
- **Intervention:** interventionID
- **LocalMap:** regionName
- **Port:** name (assuming port names are unique within a location/map
  context, though `name` is the standard identifier provided)

#### Integrity Constraints

- **Location:** `postalCode` must be unique.
- **Port:** `services` must contain at least one value (`[1..*]`).
- **Evaluation:** `impactScore` must be an integer between 1 and 10.
- **EnvironmentalTechnician:** A single technician performs the
  evaluation.

#### Derived Information

- **Port: `/candidateInterventions`**: Represents interventions
  calculated by the system based on the impact of interventions in ports
  with similar characteristics, rather than executed interventions.
