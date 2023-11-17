# PRAC 1
Alejandro Pérez Bueno
Nov 17, 2023

- [Self-Responsibility Declaration](#self-responsibility-declaration)
- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)
  - [a) One requirement conflict](#a-one-requirement-conflict)
  - [b) Two requrements depend on each
    other](#b-two-requrements-depend-on-each-other)
- [Question 5](#question-5)
- [Question 6](#question-6)
  - [a) Five user-level use cases](#a-five-user-level-use-cases)
  - [b) Two task-level use cases](#b-two-task-level-use-cases)



## Self-Responsibility Declaration

> I understand that plagiarism, the use of AI or other generated content
> will imply that the delivered work will not be reviewed and it will be
> automatically assigned a grade of D. I certify that I have completed
> the CAT1 individually and only with the help that the professors of
> this subject considered appropriate, according to the FAQs about
> plagiarism.



## Question 1

|                                                                         Requirement                                                                         |                                                                                                            Description                                                                                                            |    Type    |                         Stakeholder                         |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----------:|:-----------------------------------------------------------:|
|            The new version must be more scalable and maintainable, so that adding new functionality or modifying the code is not a complex task.            |       The system must be designed in a way that it can accommodate new features and modifications easily without disrupting the existing functionality. The system should be scalable to support increasing users and data.       | Technical  |          Sara Marquez, CTO and Development Manager          |
| The database should only be accessible through the internal network and all data consumption through the applications should be done through a backend API. | The system should ensure that the data is secure and only accessible to authorized personnel. The data flow between the applications and the database should be done through a secure backend API to prevent unauthorized access. |  Security  |                João Alves, software engineer                |
|                   The application should support at least the English language, for runners of other nationalities to be able to use it.                    |             The system must be accessible to a wider audience, including non-native English speakers. The user interface and content should be available in English to ensure that it is understandable to all users.             | Linguistic | Marta López, regular runner, coach, and user of the service |

## Question 2

These are user roles mentioned in the interviews:

1.  Founder and CEO of ChipRun
2.  Head of the Customer Department
3.  Race organizer and regular customer
4.  Regular runner, coach, and user of the service
5.  Software engineer and member of the application development team.
6.  Follower of the runner
7.  Coach of the runner
8.  New (unregistered) user of the platform
9.  Online payment in platform user

## Question 3

User stories to represent functional requirements:

1.  As a **coach**, I want to be able to **add comments and training
    plans to the races of the runners I train** so that I can **analyze
    their performance and help them improve their times**.
2.  As a **regular runner**, I want to be able to view the **history of
    the races I have participated in** and see my **final and partial
    times, pace, distance of the race, number of runners who took part
    and finishing position** so that I can **track my progress and set
    new goals**.
3.  As a **follower**, I want to be able to **follow the runner in
    real-time and see their partial times** so that I can keep track of
    how family menbers are doing on a specific race.
4.  As an **online payment** in platform user, I want to be able to
    **pay the registration fee through an online payment platform using
    a credit card** so that I can efficiently **sign up for races**.

## Question 4

### a) One requirement conflict

The regular runner wants to see their race history, while the coach
wants to add notes and training schedules to the runners’ races. The
issue comes from the possibility that the runner does not want to
divulge important information in the coach’s remarks and training
schedules. Because they must monitor their trainees’ development and
offer advice for improvement, coaches are interested in this need. The
criteria interests the runner because it allows them to monitor their
development and establish new objectives. The regular runner asserts
that he has a right to see his own race history, while the coach claims
that it is essential for the runner’s development.

### b) Two requrements depend on each other

On the one hand, organizers want to set up ways to allow runners to pay
from their platforms online with a credit card, and on the other hand
users of the platform need this payment system as well. Thus, the two
requirements depend on one another in order to be completed, and if
either organizers don’t set up the payment method or if runners do not
pay online with a credit card, both requirements will be useless on
their own.

## Question 5

- **Use case identifier**: Sign up for a popular race

- **Principal actor**: Runner

- **Supporting actors**: Organizer, Administrator

- **Level**: User-level

- **Scope**: System

- **Main success scenario**:

  1.  The runner logs in or signs up in the app.
  2.  The runner reviews the available races on the app.
  3.  The runner clicks on the registration option for the desired race.
  4.  The runner inputs their personal data in the race registration
      form.
  5.  The runner selects the option *automatically enter saved data* in
      case they want to use information provided for past races or
      inputs the data manually if there is no previous data.
  6.  The runner adds special requests if needed.
  7.  The runner attaches any required documents, such as a information
      on allergies or health conditions to consider.
  8.  The runner pays the registration fee through an online payment
      platform using a credit card.
  9.  The registration is saved and pending confirmation by the
      organizer.
  10. The runner receives a confirmation email once the organizer has
      validated the registration.

- **Alternative scenarios**:

  1.  In step 1, the runner does not remember their password. The runner
      clicks an option to send an email with instructions to reset it.
  2.  In step 7, the attached document format is not valid. The runner
      is notified and must provide a valid PDF document before the
      registration can be confirmed.
  3.  In step 8, the payment fails. The runner is notified and must
      provide a valid payment method before the registration can be
      confirmed.

## Question 6

### a) Five user-level use cases

1.  Create a new race: The organizer creates a new race and adds all the
    necessary information such as date, location and registration fees.
2.  Modify a race: The organizer modifies a race that has already been
    created, changing information mentioned in the last use case.
3.  Delete a race: The administrator deletes a race that has been
    created by an organizer but does not comply with the minimum quality
    standards (contains false information, does not meet companies
    standards, and so on).
4.  Add a professional runner: The organizer adds a professional runner
    to a race to increase its popularity and promote this runner.
5.  Validate a registration document: The organizer validates a
    registration document that has been sent by a runner during the
    registration process.

### b) Two task-level use cases

1.  Use case for *Create a new race*: Add race categories: The organizer
    adds different race categories to a race, such as age groups or
    gender categories, and sets the registration fee for each category.
2.  Use case for *Validate a registration document*: Verify the document
    format: The organizer verifies that the attached registration
    document is in a valid format (PDF), and notifies the runner if the
    format is invalid.
