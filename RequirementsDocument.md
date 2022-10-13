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

| Use case # 1      ||
| ------------------ |--|
| Name              | Create Account |
| Users             | Student and Faculty  |
| Rationale         | A user should be able to create a new account in order to save their information and login in the future. |
| Triggers          | The user selects an option to create a new account.  |
| Preconditions     | The user is on the login page, but not logged in. |
| Actions           | 1. The user indicates that the software is to create a new account. <br>2. The software responds by routing to a page to create an account.  <br>3. The user inputs an username (a WSU email) and password, contact information (firstname, lastname, WSU ID, email, and phone number). <br>4. The software checks if the new account is valid.|
| Alternative paths | 1. In Step 3, if the user is a student, they may add some additional information (major, cumulative GPA, expected graduation date, etc.), and the student may select courses they have served as a TA.<br>2. In Step 4, the software finds that the new account information is invalid and allows the user to try again. The software then indicates which fields are invalid. <br>3. At any point in steps 1-3, the user may decide to abort new account creation. In this case, the software returns to the precondition state. |
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
| Acceptance tests  | Make sure that the student successfully applied to an open TA position.  |
| Iteration         | Iteration 2  |

| Use case # 4      ||
| ------------------ |--|
| Name              | Check status of TA applications and withdraw pending applications.  |
| Users             | Student  |
| Rationale         | The user must be able to check the status of their current TA applications.  |
| Triggers          | User selects an option to view their TA applications.  |
| Preconditions     | 1. User must have applied to one or more TA positions. <br>2. User must be logged in  |
| Actions           | 1. User indicates that the software is to allow the user to view their TA applications. <br>2. Software displays list of the user's TA applications. Software will display "Pending" if the application is submitted, and "Assigned" if the application has been accepted by faculty. Pending applications will have an option to withdraw. <br>3. User chooses to withdraw a pending TA application. <br>4. The software removes the user's TA application.|
| Alternative paths | 1. In Step 3, the user may not choose to withdraw a pending application. In this case, the software will keep displaying all the user's TA applications. |
| Postconditions    | The user-selected pending application is withdrawn. |
| Acceptance tests  | Make sure the chosen application has been withdrawn. |
| Iteration         | Iteration 3  |

| Use case # 5      ||
| ------------------ |--|
| Name              | Create TA positions |
| Users             | Faculty |
| Rationale         | Faculty users must be able to create TA positions or there would be no TA positions for student users to apply to. |
| Triggers          | A faculty user selects an option to create new TA positions. |
| Preconditions     | User must be logged in. |
| Actions           | 1. The user indicates that the software is to create a new TA position. <br>2. The software responds by routing to a page to create a new TA position. This page will ask the user to choose a course for the TAship (from a predetermined list of courses), number of TA's needed for the course, qualifications for the TAship, and the year and semester for the TAship.<br>3. The user enters the required information. <br>4. The software validates inputs and creates the new TA position.|
| Alternative paths | 1. Anytime in steps 1-3, the user may abort TA position creation. In this case, the user is returned to the previous page.<br> 2. In Step 4, the user inputs may not be valid. In this case, the software will prompt the user for inputs again. |
| Postconditions    | The TA position was successfully created.  |
| Acceptance tests  | Make sure the TA position was created. |
| Iteration         | Iteration 1 |

| Use case # 6      ||
| ------------------ |--|
| Name              | View and select from a list of TA applicants and their qualifications. |
| Users             | Faculty  |
| Rationale         | Faculty users must be able to view a list of applicants for a TA position. Faculty users also must be able to view the applicant's qualifications, and select an applicant to assign to a TA position they have created. |
| Triggers          | The user selects an option to view a list of applicants to TA positions they have created.  |
| Preconditions     | 1. The faculty user must have created at least one TA position. <br>2. The user must be logged in.<br>3. There must be at least one application for one of the user's created TA positions.|
| Actions           | 1. The user indicates that the software is to display a list of applicants to all of their created TA positions. <br>2. The software responds by displaying a list of applicants and their qualifications to the user's created TA positions. <br>3. The user selects an option to assign an applicant to the TA position applied for. <br>4. The software assigns the applicant to the given TA position. |
| Alternative paths | 1. In Step 3, the number of TA's needed for the TA position may already be fulfilled. In this case, the software will not allow the applicant to be assigned to the TA position, and will continue dispaying the list of all applicants. <br>2. In Step 3, the user may not choose to assign the applicant to the TA position. In this case, the software would continue displaying the list of all applicants. <br>3. In Step 3, the applicant may already be assigned to a TA position. In this case, the software returns to displaying the list of all applicants (Step 2). |
| Postconditions    | The selected applicant is assigned to the TA position applied for. |
| Acceptance tests  | Make sure the student applicant is assigned to the TA position they applied for. |
| Iteration         | Iteration 3 |

| Use case # 7      ||
| ------------------ |--|
| Name              | Edit user account information. |
| Users             | Student and Faculty  |
| Rationale         | All users must be able to edit their account information. |
| Triggers          | The user selects an option to edit their account information. |
| Preconditions     | The user must be logged in. |
| Actions           | 1. The user indicates that the software is to allow them to edit their account information. <br>2. The software responds by requesting new contact information (firstname, lastname, WSU ID, email, phone), additional information (major, cumulative GPA, expected graduation date, etc.) and courses the user has served as TA before. <br>3. The user inputs their updated information. <br>4. The software replaces the user's old account information with the new user input. |
| Alternative paths | 1. In Step 2, the user may not be a student. In this case, the software will only request that the user input contact information. <br>2. At any time, the user may abort the process of editing their account information. In this case, the software returns to the index page. |
| Postconditions    | The user's information is successfully updated. |
| Acceptance tests  | Make sure that the user's information was successfully edited. |
| Iteration         | Iteration 2 |

| Use case # 8      ||
| ------------------ |--|
| Name              | Logout. |
| Users             | Student and Faculty  |
| Rationale         | All users must be able to logout of their account.  |
| Triggers          | The user selects the logout button to sign out of their account  |
| Preconditions     | The user must be logged in  |
| Actions           | 1. The user indicates to the software to log the user out of their account. <br> 2. The Software responds by reloading the page to a view in which the user can no longer access the website as if they are in an account. <br>3. The Software also ensures their account information is in the database for login. |
| Alternative paths | 1. In step 2, the user may have accidentally logged out of their account. In this case, the software will keep all current information of the user. When the user logs back into their account, they will be taken to the main page with an updated version where they have access as a user.   |
| Postconditions    | The user will be successfully logged out and shown the base main page |
| Acceptance tests  | Make sure the user is logged out and can't make changes as if they are logged in  |
| Iteration         | Iteration 1  |

## Swimlane Diagram

![alt text](https://github.com/dp1488/Term-Project-322/blob/Jerel/swimdiagram.JPG)

----
## 2.3 Non-Functional Requirements

1. [Account Safety]:  [When signing in, the user information should be stored in the database, only accessible to the user.]
2. [Faculty Information]:  [The Faculty should be able to see all users that apply to be TAs for their class. They should not be able to see other teachers TA information.]
3. [Design Constraints]:  [The user should be able to smoothly transition between pages in a non-round-a-bout manner. The layout of each page should be easy to navigate with no excess effects or links. ]
4. [Reusability Methods]:  [The user should be able to go through the process of signing up for as many classes as are available. Each user can only sign up for a class once.]
5. [Safety and Security]:  [The user (Whether faculty or student) should be able to confidently sign in to and go through the process of signing up without thoughts of security breaches.]
6. [Scalability ]:  [The software and database should be able to continuously preform well even with an increase in user and information volume.]
7. [Portability ]:  [The webpage should be accessible on all devices. Ex: Phone, Computer, Tablet.]
8. [Dependability ]:  [The webpage would have a dependible UI with no room for routing errors. Would also be an overall safe system for personal information.]

----
# 3. User Interface

Sample Faculty UI

![alt text](https://github.com/dp1488/Term-Project-322/blob/4e35aa151a7fa43a9dcfbf736ae5c6ebc6db4969/UserInterfaceSketch-Faculty%20UI.jpg)

Sample Student UI

![alt text](https://github.com/dp1488/Term-Project-322/blob/4e35aa151a7fa43a9dcfbf736ae5c6ebc6db4969/UserInterfaceSketch-Student%20UI.jpg)

----
# 4. References

Cite your references here.

For the papers you cite give the authors, the title of the article, the journal name, journal volume number, date of publication and inclusive page numbers. Giving only the URL for the journal is not appropriate.

For the websites, give the title, author (if applicable) and the website URL.

----
----
