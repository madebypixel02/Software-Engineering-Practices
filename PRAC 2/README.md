# PRAC 2
Alejandro Pérez Bueno
Dec 29, 2023

-   [Self-Responsibility Declaration](#self-responsibility-declaration)
-   [Question 1](#question-1)
-   [Question 2](#question-2)
-   [Question 3](#question-3)
    -   [a) UML class diagram](#a-uml-class-diagram)
    -   [b) Keys, derived information &
        constraints](#b-keys-derived-information-constraints)
-   [Question 4](#question-4)
    -   [a) UML class diagram](#a-uml-class-diagram-1)
    -   [b) Keys, derived information &
        constraints](#b-keys-derived-information-constraints-1)
-   [Annexes](#annexes)



## Self-Responsibility Declaration

> I understand that plagiarism, the use of AI or other generated content
> will imply that the delivered work will not be reviewed and it will be
> automatically assigned a grade of D. I certify that I have completed
> the PRAC2 individually and only with the help that the professors of
> this subject considered appropriate, according to the FAQs about
> plagiarism.



## Question 1

> **Note**
>
> See [Figure 1](#fig-question1)

## Question 2

> **Note**
>
> See [Figure 2](#fig-question2)

Other additional use cases:

-   Anonymous User: Search for races
-   Follower: View runner’s progress
-   Coach: Create training plan for a specific runner
-   Organizer: Edit race details
-   Admin: Ban user from the platform

## Question 3

### a) UML class diagram

> **Note**
>
> See [Figure 3](#fig-question3)

### b) Keys, derived information & constraints

> **Warning**
>
> Note, the attribute for the user should be passportNumber, rather than
> idNumber

#### Keys

-   Race: primary key is a combination of name, date, and distanceUnit.
-   Runner: primary key is passportNumber.
-   Registration: primary key is bibNumber, and foreign keys are
    runner’s passportNumber and race’s name, date, and distanceUnit.
-   TimingPoint: primary key is a combination of race’s name, date,
    distanceUnit, and distanceValue.
-   FinalResult: primary key is the same as the Registration’s
    bibNumber.

#### Derived Information

-   FinalResult’s pace is calculated based on the race distance and the
    runner’s total time.

#### Constraints

-   Two Races with the same name, on the same date, and with the same
    defined distance cannot exist.
-   TimingPoints are only applicable to a Race, and it must be ensured
    that there are no two repeated points in the same race.
-   If a maximum number of participants is defined for a Race, the
    number of registrants cannot exceed it.
-   Every Race will always have at least two TimingPoints: the moment of
    the start and the finish line.
-   If a runner does not finish the race, the pace cannot be calculated
    and will be left without value.
-   The racer’s passport consists of three characters followed by six
    digits.
-   distanceValue can only contain one character, which must be a valid
    currency (e.g. `€`, `$`, etc.).

## Question 4

### a) UML class diagram

> **Note**
>
> See [Figure 4](#fig-question4)

### b) Keys, derived information & constraints

-   User: The primary key is email. The textual integrity constraint is
    that email must be unique.
-   Coach: The primary key is the same as the User it represents, which
    is email.
-   Group: The primary key is the combination of the Coach’s email and
    the name of the Group. The textual integrity constraint is that the
    name of the Group must be unique for each Coach.
-   Follower: There is no primary key for this class, as it serves as a
    many-to-many relationship between Users and Runners.
-   Organizer: The primary key is the same as the User it represents,
    which is email.

## Annexes

<img src="./img/Sign_up_Register_for_a_popular_race.png"
id="fig-question1"
alt="Figure 1: “Sign up (Register) for a popular race” Activity diagram" />

<img src="./img/Race_Use_Case_Diagram.png" id="fig-question2"
alt="Figure 2: Race Use Case" />

<img src="./img/Race_Class_Diagram.png" id="fig-question3"
alt="Figure 3: Race Class" />

<img src="./img/Race_Class_Diagram-2.png" id="fig-question4"
alt="Figure 4: Updated Race Class" />
