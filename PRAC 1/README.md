# PRAC 1
Alejandro Pérez Bueno
Apr 04, 2025

- [Self-Responsibility Declaration](#self-responsibility-declaration)
- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
  - [Functional Requirements in User Story
    Format](#functional-requirements-in-user-story-format)
  - [Acceptance Tests for the Example User
    Story](#acceptance-tests-for-the-example-user-story)
- [Question 4](#question-4)
- [Question 5](#question-5)
- [Question 6](#question-6)
  - [Existing User-Level Use Cases](#existing-user-level-use-cases)
  - [New User-Level Use Cases Consistent with the
    Context](#new-user-level-use-cases-consistent-with-the-context)
  - [Task-Level Use Cases for *a* and
    *b*](#task-level-use-cases-for-a-and-b)



## Self-Responsibility Declaration

> I certify that I have completed Practice 1 entirely on my own and
> solely with the assistance deemed appropriate by the course
> instructors, according to the guidelines explained in the Originality
> in Assessment section of the classroom.
>
> I understand that non-original work and/or the use of generative AI
> will result in the submitted activity not being graded and will
> automatically receive a score of 0.

## Question 1

Below are three non‐functional requirements identified from the
statement:

- Requirement 1
  - Phrase: *I would like the application to have a visual appearance in
    line with the company’s colors and aesthetics…*
  - Description: The user interface must reflect the company’s brand
    identity by using its specific colors, design elements, and overall
    aesthetic, thereby making the application immediately recognizable
    as a WeddingWorld tool.
  - Type: *Look and feel requirement*
  - Stakeholder: *Alba*
- Requirement 2
  - Phrase: *the application must be available both as a web version and
    as a mobile app for smartphones (Android and iOS).*
  - Description: The system has to be developed for multiple platforms,
    ensuring that it runs consistently on desktop browsers as well as on
    native mobile devices (Android and iOS), so users can access it in
    different environments.
  - Type: *Portability requirement*
  - Stakeholder: *Pablo*
- Requirement 3
  - Phrase: *the application should support 1,000 concurrent users under
    normal conditions but must be able to handle spikes of up to 5,000
    concurrent users.*
  - Description: The system must be engineered to maintain acceptable
    performance under typical usage (1,000 users simultaneously) and be
    scalable enough to manage significant load increases (up to 5,000
    concurrent users) during busy periods.
  - Type: *Performance/scalability requirement*
  - Stakeholder: *Estefanía*

## Question 2

User roles:

- *Wedding Planner*
- *Wedding Couple*
- *Guest*
- *Service Provider*

## Question 3

### Functional Requirements in User Story Format

1.  Virtual Event Board
    - User Story: **As a wedding planner I want a virtual event board to
      add confirmed wedding events so that couples can easily keep track
      of the wedding day schedule.**
    - Phrase: “The first functionality I want to implement is the
      virtual event board. This is a shared virtual board between the
      spouses and the wedding planner, where the assigned wedding
      planner will chronologically add all the confirmed events for the
      wedding day.”
2.  Wedding Invitation Process
    - User Story: **As a wedding planner I want to register weddings and
      send email invitations to couples so that they can confirm their
      wedding details.**
    - Phrase: “The virtual invitation process should work as follows:
      The responsible wedding planner will access the application and
      register the wedding. The first step will be to associate both
      spouses with the newly created wedding. Once linked by the wedding
      planner, the couple will receive an email with a link allowing
      them to register and confirm that this is indeed their wedding.”
3.  Public Registration Link for Guests
    - User Story: **As a couple I want to share a public registration
      link with guests so that only invited guests can register and be
      linked to our wedding.**
    - Phrase: “I would prefer if the wedding within the application had
      a public link, visible only to us (the couple), which we could
      share with guests so they can register and link themselves to the
      wedding through this link. However, before finalizing the linkage,
      we would validate that the person is indeed an invited guest.”
4.  Direct Service Provider Registration
    - User Story: **As a service provider I want to register and publish
      my services directly in the application so that I can quickly
      update details such as pricing and discounts without an
      intermediary.**
    - Phrase: “As a provider, I would like to be able to register in the
      application and publish my services directly, without having to go
      through an intermediary from Alba’s company.”

### Acceptance Tests for the Example User Story

1.  **Upload Process Verification**
    - Test that when a guest selects the upload option and chooses a
      valid photo file (e.g., JPEG or PNG), the image is successfully
      uploaded and immediately displayed in the wedding photo gallery
      with the correct timestamp and attribution.
2.  **File Format and Size Handling**
    - Test that the system accepts only supported image formats (such as
      JPEG and PNG) and enforces any file size limits by displaying a
      clear error message if a guest attempts to upload a file that is
      in an unsupported format or exceeds the size limit.
3.  **User Interface Feedback**
    - Test that after a successful upload, the application shows a
      visible progress indicator during the upload process and a
      confirmation message once the upload is complete, ensuring that
      the guest is aware that their photo has been added to the gallery.

## Question 4

A clear conflict arises regarding the commission fee imposed on service
providers:

- Stakeholders involved:
  - *Alba* (Wedding planner and CEO of WeddingWorld) and *Pablo*
    (Financial Director) support charging a commission.
  - *Nuria* (Event Restaurant Manager and service provider) opposes any
    commission fees.
- Requirement 1: “Charge a small commission to the provider for
  acquiring a new client through our platform.”
  - Alba and Pablo argue that this commission creates an additional
    revenue stream that helps cover maintenance costs and contributes to
    the financial sustainability of the application.
- Requirement 2: “I would not be in favor of being charged a commission
  for publishing our services or for being booked through the
  application.”
  - Nuria explains that eliminating commission fees would allow
    providers like her to register and update their service details more
    directly and efficiently, thereby facilitating quicker service
    updates and reducing financial burdens on the providers.

## Question 5

- **Use Case Identifier:** UC-VWI-01 (Sending Virtual Wedding
  Invitations)
- **Actor Principal:** *Wedding Planner* (Alba)
- **Supporting Actors:**
  - *Spouses* (Couple)
  - *Guests*
- **Level:** *User goal* (high-level functionality that supports the
  wedding management process)
- **Scope:** *Wedding Management Application*
- **Main Stage of Success:**
  1.  The wedding planner accesses the application and creates a new
      wedding record.
  2.  The wedding planner associates both spouses with the wedding.
  3.  Once associated, each spouse receives an email containing a
      registration link to confirm that the wedding details are correct.
  4.  After the spouses confirm their registration, the wedding planner
      inputs the guest list (using the provided and authorized email
      addresses).
  5.  Guests receive a virtual invitation via email that includes a link
      to register on the application.
  6.  Interested guests register (if they choose) and confirm their
      attendance directly within the application.
  7.  The use case completes once the guests’ attendance has been
      confirmed.
- **Alternative Scenarios:**
  1.  **Spouse Email Error:** If the wedding planner enters an incorrect
      email address for one or both spouses, the registration email is
      not received. In this case, the spouses must notify the wedding
      planner or the planner must verify and re-enter the correct email
      addresses before resending the invitation.
  2.  **Optional Guest Registration:** Some guests may choose not to
      register in the application. In these cases, although they still
      receive the virtual invitation by email, no further confirmation
      is performed within the app.
  3.  **Guest Declines Invitation:** A guest might register on the
      application but then actively decline the invitation. This outcome
      is documented, and the guest is marked as not attending, prompting
      the wedding planner to follow up or update their list accordingly.

## Question 6

### Existing User-Level Use Cases

1.  **Sending Virtual Wedding Invitations**
    - Main actor: *Wedding Planner*
    - Brief Description: The wedding planner creates a new wedding
      record, associates the spouses, inputs the guest list, and the
      system automatically sends invitation emails to guests so that
      they can confirm their attendance.
2.  **Direct Service Provider Registration**
    - Main actor: *Service Provider*
    - Brief Description: A service provider registers in the application
      and publishes his or her services directly, thereby updating
      information such as pricing and discounts without intermediary
      intervention.

### New User-Level Use Cases Consistent with the Context

1.  **Manage Wedding Budget**
    - Main actor: *Couple*
    - Brief Description: The couple can track and manage all
      wedding-related expenses, enter cost items, view budget summaries,
      and adjust allocations, ensuring that they remain within their
      planned spending.
2.  **Manage Service Bookings**
    - Main actor: *Service Provider*
    - Brief Description: A service provider can view, confirm, and
      manage the bookings received through the application, including
      checking details of each booking and updating availability
      accordingly.

### Task-Level Use Cases for *a* and *b*

**“Sending Virtual Wedding Invitations”** (Main actor: *Wedding
Planner*)

- **Task-Level Use Case 1:** Create Wedding Record and Associate Spouses
  - Description: The wedding planner enters wedding details and
    associates both spouses to the newly created wedding record. This
    task ensures that the couple receives the registration email to
    confirm their wedding details.
- **Task-Level Use Case 2:** Input Guest List and Initiate invitation
  Email
  - Description: The wedding planner inputs the list of guest email
    addresses, verifies their correctness, and triggers the system to
    send out virtual invitation emails so that guests can register and
    confirm their attendance.

**“Manage Wedding Budget”** (Main actor: *Couple*)

- **Task-Level Use Case 1:** Record New Expense Item
  - Description: The couple enters details for a new expense (such as
    amount, category, and date) into the application, thereby updating
    their wedding cost records.
- **Task-Level Use Case 2:** View and Update Budget Overview
  - Description: The couple accesses the current budget summary, reviews
    expense totals against their planned budget, and makes adjustments
    to budget allocations if necessary.
