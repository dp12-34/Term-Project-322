# Software Requirements Specification

## Your Project Title
TA Student APP
Prepared by:

* `Drew Price`,`School`
* `Caden Silberlicht`,`Washington State University`
* `<Jerel Santos>`,`<School>`
* `Carson Loveless`,`Washington State University`

---

**Course** : CptS 322 - Software Engineering Principles I

**Instructor**: Sakire Arslan Ay

---

## Table of Contents
- [Software Requirements Specification](#software-requirements-specification)
  - [## Your Project Title](#-your-project-title)
  - [Table of Contents](#table-of-contents)
  - [Document Revision History](#document-revision-history)
- [1. Introduction](#1-introduction)
  - [1.1 Document Purpose](#11-document-purpose)
  - [1.2 Product Scope](#12-product-scope)
  - [1.3 Document Overview](#13-document-overview)
- [2. Requirements Specification](#2-requirements-specification)
  - [2.1 Customer, Users, and Stakeholders](#21-customer-users-and-stakeholders)
  - [2.2 Use Cases](#22-use-cases)
  - [2.3 Non-Functional Requirements](#23-non-functional-requirements)
- [3. User Interface](#3-user-interface)
- [4. References](#4-references)
- [Appendix: Grading Rubric](#appendix-grading-rubric)

<a name="revision-history"> </a>

## Document Revision History

| Name | Date | Changes | Version |
| ------ | ------ | --------- | --------- |
|Revision 1 |2022-10-05 |Initial draft | 1.0        |
|      |      |         |         |
|      |      |         |         |

----
# 1. Introduction

This document will highlight our plans for the TA web application, it's user stories, use cases, stakeholders, customers, and what basic requirements it will need to be fully functional.

## 1.1 Document Purpose

The intended audience is our professor/TAs who will grading and reviewing our web application

## 1.2 Product Scope

We are making a web application (the TA web app) that allows students to apply for a TA position, and for Professors to choose TA's amongst applications. This service will allow for a quick and streamlined experience for all relevant parties. Our goal is to make this a user friendly experience for anyone new to the interface. 

## 1.3 Document Overview

In the next section wse will be going over specifications for this project including a information about the many diffent users, their user stories, the use cases for the involved parties, and  our non-functional requirments. Finally, we will show about prototypes and/or mock-ups for our main interface. 

----
## 2. Requirements Specification

This section specifies the software product's requirements.

## 2.1 Customer, Users, and Stakeholders

The customers will include all professors who are looking to hire TA/TAs, where the users of this application are those professors, and the students who are looking to become TA's. The stakeholders are out Professor Sakire Arslan Ay and here Associates (TA's)

## 2.2 Use Cases

This section will include the specification for your project in the form of use cases. The section should start with a short description of the actors involved (e.g., regular user, administrator, etc.) and then follow with a list of the use cases.

For each use case you should have the following:

* Name,
* Actors,
* Triggers (what initiates the use case),
* Preconditions (in what system state is this use case applicable),
* Actions (what actions will the code take to implement the use case),
* Alternative paths
* Postconditions (what is the system state after the use case is done),
* Acceptance tests (list one or more acceptance tests with concrete values for the parameters, and concrete assertions that you will make to verify the postconditions).

Each use case should also have a field called "Iteration" where you specify in which iteration you plan to implement this feature.

You may use the following table template for your use cases. Copy-paste this table for each use case you will include in your document.

| Use case # 1      ||
| ------------------ |--|
| Name              | Create Account |
| Users             | Student and Faculty  |
| Rationale         | A user should be able to create a new account in order to save their information and login in the future. |
| Triggers          | The user selects an option to create a new account.  |
| Preconditions     | The user is on the login page (they are not yet logged in). |
| Actions           | 1. The user indicates that the software is to create a new account. <br>2. The software responds by routing to a page to create an account.  <br>3. The user inputs an username (a WSU email) and password, contact information (firstname, lastname, WSU ID, email, and phone number). <br>4. The software checks if the new account is valid and updates the database.|
| Alternative paths | 1. In Step 3, if the user is a student, they may add some additional information (major, cumulative GPA, expected graduation date, etc.), and the student may select courses they have served as a TA.<br>2. In Step 4, the software finds that the new account information is invalid and does not update the database. The software then indicates which fields are invalid. <br>3. At any point in steps 1-3, the user may decide to abort new account creation. In this case, the software returns to the precondition state. |
| Postconditions    | The user succesfully creates a new account.  |
| Acceptance tests  | Make sure the new account is created and added to the database.  |
| Iteration         | Iteration 1|

| Use case # 2      ||
| ------------------ |--|
| Name              | Login.  |
| Users             | Student and Faculty  |
| Rationale         | Users must be able to login to view any information on the webpage. |
| Triggers          | The user selects an option to login. |
| Preconditions     | The user is not currently logged in.  |
| Actions           | 1. The user indicates that the software is to allow them to login. <br>2. The software responds by routing to the login page. <br>3. The user inputs their username and password. <br>4. The software verifies the user login and routes to index page.|
| Alternative paths | 1. In Step 4, if the username does not exist or the password is incorrect, the software notifies the user and allows them to input username and password again. <br>2. At any step 1-3, the user may abandon their login attempt. In this case the user must stay on the login page as they must be logged in to view other pages. |
| Postconditions    | The user successfully logs in. |
| Acceptance tests  | Must make sure the user is successfully logged in.  |
| Iteration         | Iteration 1  |

| Use case # 3      ||
| ------------------ |--|
| Name              | View and apply for open TA positions.  |
| Users             | Student  |
| Rationale         | The student must be able to view a list of TA positions and apply for one of them.  |
| Triggers          | The user selects an option to view available TA positions.  |
| Preconditions     | User is logged in. |
| Actions           | 1. The user indicates that the software is to allow them to view open TA positions. <br>2. The software displays open TA positions and their information (course title, semester, instructor's name and information, and qualifications needed.) and an option to apply for each of them. <br>3. The user selects an option to apply for a TA position. <br>4. The software responds by requesting inputs from the user (grade earned in course, the year and semester they took the course, and the year and semester for which they are applying to be a TA). <br>5. The user inputs all requirements. <br>6. The software validates inputs and applies the user to the TA position. |
| Alternative paths | 1. In Step 2, the software may also display recommended TA positions under another tab. The user may view this alternate tab, they can then choose to apply to a TA position. <br>2. In step 3-5, the user may at any time abort the application process. In this case, the software would return to the list of open TA positions.  |
| Postconditions    | The user successfully applies to a TA position, or does not attempt to apply to a TA position. |
| Acceptance tests  | Make sure that the student successfully applied to an open TA position and make sure the database is updated.  |
| Iteration         | Iteration 2  |

| Use case # 4      ||
| ------------------ |--|
| Name              | View and check status of TA applications.  |
| Users             | Student  |
| Rationale         | "enter your reponse here"  |
| Triggers          | "enter your reponse here"  |
| Preconditions     | "enter your reponse here"  |
| Actions           | "enter your reponse here"  |
| Alternative paths | "enter your reponse here"  |
| Postconditions    | "enter your reponse here"  |
| Acceptance tests  | "enter your reponse here"  |
| Iteration         | "enter your reponse here"  |

| Use case # 5      ||
| ------------------ |--|
| Name              | Create TA positions |
| Users             | Faculty  |
| Rationale         | "enter your reponse here"  |
| Triggers          | "enter your reponse here"  |
| Preconditions     | "enter your reponse here"  |
| Actions           | "enter your reponse here"  |
| Alternative paths | "enter your reponse here"  |
| Postconditions    | "enter your reponse here"  |
| Acceptance tests  | "enter your reponse here"  |
| Iteration         | "enter your reponse here"  |

| Use case # 6      ||
| ------------------ |--|
| Name              | View and select from a list of TA applicants and their qualifications. |
| Users             | Faculty  |
| Rationale         | "enter your reponse here"  |
| Triggers          | "enter your reponse here"  |
| Preconditions     | "enter your reponse here"  |
| Actions           | "enter your reponse here"  |
| Alternative paths | "enter your reponse here"  |
| Postconditions    | "enter your reponse here"  |
| Acceptance tests  | "enter your reponse here"  |
| Iteration         | "enter your reponse here"  |

| Use case # 7      ||
| ------------------ |--|
| Name              | Edit user information. |
| Users             | Student and Faculty  |
| Rationale         | "enter your reponse here"  |
| Triggers          | "enter your reponse here"  |
| Preconditions     | "enter your reponse here"  |
| Actions           | "enter your reponse here"  |
| Alternative paths | "enter your reponse here"  |
| Postconditions    | "enter your reponse here"  |
| Acceptance tests  | "enter your reponse here"  |
| Iteration         | "enter your reponse here"  |

| Use case # 8      ||
| ------------------ |--|
| Name              | Logout. |
| Users             | Student and Faculty  |
| Rationale         | "enter your reponse here"  |
| Triggers          | "enter your reponse here"  |
| Preconditions     | "enter your reponse here"  |
| Actions           | "enter your reponse here"  |
| Alternative paths | "enter your reponse here"  |
| Postconditions    | "enter your reponse here"  |
| Acceptance tests  | "enter your reponse here"  |
| Iteration         | "enter your reponse here"  |


**Include a swim-lane diagram that illustrates the message flow and activities for following scenario:**
“A student applies to a research position; initially its status will appear as “Pending”. The faculty who created that position reviews the application and updates the application status to either “Approved for Interview”, or “Hired”, or “Not hired”. The updated status of the application is displayed on the student view.
The student may delete the pending applications (i.e., whose status is still “Pending”. )”


----
## 2.3 Non-Functional Requirements

List the non-functional requirements in this section.

You may use the following template for non-functional requirements.

1. [Enter a Concise Requirement Name]:  [provide a concise description, in clear and easily understandable language to specify the requirement]

----
# 3. User Interface

Here you should include the sketches or mockups for the main parts of the interface.

----
# 4. References

Cite your references here.

For the papers you cite give the authors, the title of the article, the journal name, journal volume number, date of publication and inclusive page numbers. Giving only the URL for the journal is not appropriate.

For the websites, give the title, author (if applicable) and the website URL.

----
----
# Appendix: Grading Rubric
(Please remove this part in your final submission)

These is the grading rubric that we will use to evaluate your document. 

| Max Points  | **Content** |
| ----------- | ------- |
| 10          | Do the requirements clearly state the customers’ needs? |
| 5           | Do the requirements avoid specifying a design (note: customer-specified design elements are allowed; non-functional requirements may specify some major design requirements)? |
| | |  
|    | **Completeness** |
| 25 | Are use cases written in sufficient detail to allow for design and planning? |
| 4 | Do use cases have acceptance tests? | 
| 20 | Is your use case model complete? Are all major use cases included in the document? |
| 8 | Has the team provided an appropriate swim-lane diagram for the scenario where faculty reviews a student’s application? |
| 10 |  Are the User Interface Requirements given with some detail? Are there some sketches, mockups?  |
| | |  
|   | **Clarity** |
| 4 | Is the document carefully written, without typos and grammatical errors? |
| 2 | Is each part of the document in agreement with all other parts? |
| 2 | Are all items clear and not ambiguous? (Minor document readability issues should be handled off-line, not in the review, e.g. spelling, grammar, and organization). |
|   |   |
|    | **GitHub Issues** |
| 10 | Has the team setup their GitHub Issues page? Have they  generated the list of user stories, use-cases, created milestones, assigned use-cases (issues) to milestones?   Example GitHub repo (check the issues): https://github.com/WSU-CptS322-Fall2022/TermProjectSampleRepo/issues  |