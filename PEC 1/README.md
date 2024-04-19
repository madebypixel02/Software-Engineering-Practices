# PEC
Alejandro Pérez Bueno
Apr 19, 2024

-   [Self-Responsibility Declaration](#self-responsibility-declaration)
-   [Module 1 Questions](#module-1-questions)
    -   [Question 1](#question-1)
    -   [Question 2](#question-2)
    -   [Question 3](#question-3)
-   [Module 2 Questions](#module-2-questions)
    -   [Question 4](#question-4)
    -   [Question 5](#question-5)
    -   [Question 6. Online Bookstore
        App](#question-6.-online-bookstore-app)



## Self-Responsibility Declaration

> I understand that plagiarism, the use of AI or other generated content
> will imply that the delivered work will not be reviewed and it will be
> automatically assigned a grade of D. I certify that I have completed
> the CAT1 individually and only with the help that the professors of
> this subject considered appropriate, according to the FAQs about
> plagiarism.



## Module 1 Questions

### Question 1

1.  Model the main classes of the system following the defined
    architecture.

-   The role is *architect* and the activity is *Modeling* because the
    architect is the one in charge of defining the outline of a system,
    which includes the main classes of the system.

1.  Refine and validate the identified requirements, from the system
    domain’s perspective.

-   The role is *Functional Analyst* and the activity is *Requirements
    identification and management* because he is responsible for
    unifying the different views of the domain in a single model that is
    clear, concise, and consistent.

1.  Plan and estimate project tasks.

-   The role is *Project Manager* and the activity is *Project
    Management* because he is the one who has to organize the project to
    make sure every aspect of it goes as planned.

1.  Develop the application code from the documents made by analysts.

-   The role is *Programmer* and the activity is *Construction and
    testing* because a programmer must write the code for the
    application, following the designs appointed by analysts.

1.  Compile and package the code of the new version of the application
    and distribute it to the corresponding servers.

-   The role is *Deployment Manager* and the activity is *Maintenance
    and Re-engagning* because he is in charge of packaging a new version
    of a software coded by programmers into a server.

### Question 2

#### Project 1

> A fashion company director has requested a redesign of their online
> clothing and accessories sales website to attract younger customers.
> The marketing team believes that by redesigning, they can attract
> young people back to the website but hasn’t found a clear way to do
> so. The work will involve several different proposals, progressively
> made available to users, and based on their effectiveness with the
> target audience, they will be maintained, modified, or permanently
> removed.

-   Type of project: **Group 2**. The objective is clear (attract
    younger customers by redesigning the website), but the solution
    isn’t well-known as it involves several proposals and depends on
    user feedback.
-   Development Method: **Iterative and Incremental Life Cycle method**.
    This method allows for progressive development and testing of
    different proposals and is flexible and adaptable to changes, which
    is crucial for this project, as it involves a lot of experimentation
    and user feedback.

#### Project 2

> A banking entity is considering modernizing its bank transfer system
> from a Mainframe-based system to a more current Unix-based system.
> This critical process cannot tolerate failures, so the entity will
> hire experts, both functional and technical, to replicate the existing
> functionalities on the new platform, which must be available in their
> entirety from the first version.

-   Type of project: **Group 1**. The objective is clear (modernize the
    bank transfer system), and the solution is also well-known
    (replicating the existing functionalities on a new Unix-based
    platform).
-   Development Method: **The Classic or Waterfall Life Cycle method**.
    This method suits best projects in which the requirements and
    solutions are well-defined, and allows for a systematic and
    sequential approach (which is crucial for a project of this nature
    where no failures can be tolerated).

#### Project 3

> The legal department of a multinational corporation aims to reduce
> paper usage for ecological reasons, which would also save physical
> storage space and time. This pilot project will evaluate market
> solutions, analyze how other companies have implemented them, and
> study the extent to which the solution can be adopted by the company.
> This exploration may lead to identifying new approaches, such as
> avoiding physical document generation and digital information storage
> and indexing.

-   Type of project: **Group 4**. Neither the objective nor the solution
    are very clear, since it involves evaluating market solutions and
    studying how other companies have implemented them.
-   Development Method: **Lean and Agile Development**. It is flexible
    and allows for continuous learning and adaptation, and encourages
    experimentation and feedback.

### Question 3

My proposal for a **Group 3** project would be the following:

`Implementation of a new algorithm to suggest news articles in a popular News App`

In this case, the solution is known (the creation of a new algorithm)
but the objective is not very clear.

The News Feed is a critical part of the app’s user experience, and the
company is constantly working on ways to improve its algorithm. However,
defining what constitutes an “improved” News Feed is not
straightforward:

-   Is it one that maximizes user engagement?
-   Is it one that promotes high-quality content?
-   Is it one that helps users discover new interests?

The objective is not at all obvious and may shift over time based on
user feedback, changes in the digital media landscape, and the News
Company’s own strategic goals.

In this project, the App would need to engage in a process of discovery
and iteration to clarify its own objectives, which may involve
conducting user research to understand what people value in their News
Feed, analyzing data on how changes to the algorithm impact user
behavior, and refining the algorithm based on these insights.

The justification for this project is that even though the objective is
not very clear at the outset, improving the News Feed is crucial for
maintaining user engagement and satisfaction. By continually refining
its algorithms, the News Broadcast App can ensure that its platform
remains relevant and valuable to its users.

## Module 2 Questions

### Question 4

#### *Appliance* Abstract Class

-   **Subclassess**: HomeAppliance, OfficeAppliance
-   **Association**: an appliance is supplied by one and only one
    Supplier and a Supplier supplies one or more Appliances.
-   **Attributes**:
    -   Appliance: serialNumber
    -   HomeAppliance: powerConsumption
    -   OfficeAppliance: networkCapability (e.g., WiFi, Ethernet, etc.)
-   **Instances**:
    -   Appliance: {serialNumber: “A123B456”}
    -   HomeAppliance: {serialNumber: “C789D012”, powerConsumption:
        “800W”}
    -   OfficeAppliance: {serialNumber: “E345F678”, networkCapability:
        “WiFi, Ethernet”}

#### *Store* Class

-   **Subclassess**: BookStore, ClothingStore
-   **Association**: a store employs one or more Employees and an
    Employee works at one and only one Store.
-   **Attributes**:
    -   Store: storeName
    -   BookStore: genreSpecialty
    -   ClothingStore: clothingType (e.g., Men’s, Women’s, Children’s,
        etc.)
-   **Instances**:
    -   Store: {storeName: “General Store”}
    -   BookStore: {storeName: “Mystery Books”, genreSpecialty:
        “Mystery”}
    -   ClothingStore: {storeName: “Fashion Forward”, clothingType:
        “Women’s”}

### Question 5

1.  `size` should be protected. This will allow it to be accessible from
    instances of its subclasses `HouseForSale` and `HouseForRent`, but
    not from instances of the class `Owner`.
2.  `cadastralReference` should be private. This will make it accessible
    only by the `House` class itself, and not visible to instances of
    `HouseForSale` or `HouseForRent`.
3.  `name` should be public if we want instances of the classes `House`,
    `HouseForRent`, `HouseForSale`, and `Owner` to have access to this
    attribute.
4.  An owner can own multiple houses, and a house can have one owner.
    Thus, the multiplicity would be 1 (Owner) to many (Houses). This is
    not a polymorphic association because it doesn’t involve subclasses
    or superclass.
5.  1.  **Association**. A city can contain multiple houses, and a house
        is located in one city. This is not inheritance because a house
        is not a type of city, they are distinct entities that are
        related.
6.  1.  **Inheritance**. A MajorHolder is a specific type of Owner (one
        who owns more than a certain number of homes), so it makes sense
        for MajorHolder to inherit from Owner.

### Question 6. Online Bookstore App

#### Classes

-   HealthcareStaff (Abstract Class)
    -   Attributes: Name, Surname, ID, Date of Birth, Phone Numbers (can
        have multiple)
-   Nurse (Concrete Class, Subclass of HealthcareStaff)
    -   Attributes: Years of Experience, Supervisor (may or may not
        have)
-   Doctor (Concrete Class, Subclass of HealthcareStaff)
    -   Attributes: Resident Status, Specialties (at least one)
-   Specialty (Concrete Class)
    -   Attributes: Name, Involvement in On-call Duties
-   HealthCenter (Concrete Class)
    -   Attributes: Name, Address, Floor Number (may or may not have)

#### Associations

-   Supervision: Links each Nurse to none or one other Nurse as a
    supervisor and each Nurse can supervise multiple other Nurses. This
    is not a polymorphic association as it only involves the Nurse
    class.
-   Specialization: Connects each Doctor to at least one Specialty and
    each Specialty can be linked to multiple Doctors. This is not a
    polymorphic association as it only involves the Doctor and Specialty
    classes.
-   Assignment: Binds each HealthcareStaff to exactly one HealthCenter
    and each HealthCenter can have multiple HealthcareStaff members
    assigned to it. This is a polymorphic association as it involves the
    abstract class HealthcareStaff and its subclasses Doctor and Nurse.

> **Note**
>
> **Assumptions**
>
> -   A nurse cannot supervise him/herself.
> -   A doctor can specialize in multiple areas.
> -   Each healthcare staff member is assigned to only one health
>     center.
> -   Each health center must have at least one healthcare staff member.
> -   The phone numbers for healthcare staff are unique to each
>     individual, hence they can have multiple.
> -   The floor number for a health center is optional because not all
>     health centers may have multiple floors.
