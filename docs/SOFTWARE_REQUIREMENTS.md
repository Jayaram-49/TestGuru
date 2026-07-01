# TestGuru - Software Requirements Specification (SRS)

## 1. Introduction

### 1.1 Purpose

The purpose of this Software Requirements Specification (SRS) is to define the requirements for TestGuru, a web-based technical assessment platform. This document serves as a reference for planning, designing, developing, testing, and maintaining the application throughout its development lifecycle.

### 1.2 Scope

TestGuru is a web-based technical assessment platform that enables startups, companies, educational institutions, and training organizations to create and conduct online assessments for hiring, training, and evaluation purposes. Organizations can create assessments, generate assessment links, and share them with candidates. Candidates can register using the shared assessment link, take the assessment, and submit their responses. The platform automatically evaluates objective questions and provides results to the organization.

### 1.3 Intended Audience

This document is intended for:

- Developers
- Testers
- Future Contributors
- Project Maintainers
- Anyone interested in understanding the project requirements.

## 2. Problem Statement

Many startups, companies, and training institutes need an efficient way to conduct technical assessments during their hiring or evaluation process. Traditional methods, such as paper-based tests, email-based assessments, or generic form tools, often require significant manual effort to create tests, evaluate responses, and manage candidate information.

There is a need for a centralized platform where hiring organizations can create technical assessments, generate a unique assessment link, share it with candidates, and review the results from a single dashboard.

TestGuru aims to solve this problem by providing a secure, user-friendly, and web-based technical assessment platform that simplifies the entire assessment process for both hiring organizations and candidates.

## 3. Project Objectives

The primary objectives of TestGuru are:

- To provide a secure and user-friendly platform for conducting technical assessments.
- To enable hiring organizations to create and manage assessments efficiently.
- To allow candidates to register through a shared assessment link and complete assessments online.
- To automatically evaluate objective-type questions and generate results.
- To provide hiring organizations with a dashboard to view candidate performance and assessment results.
- To reduce the manual effort involved in conducting technical assessments.
- To provide a scalable platform that can support future enhancements and additional assessment features.


## 4. User Roles

### 4.1 Candidate

A Candidate is a user who participates in technical assessments.

Responsibilities:
- Register using a shared assessment link.
- Log in to the platform.
- View assigned assessments.
- Start and complete assessments.
- Submit responses before the time expires.
- View assessment status and results (based on organization settings).
- Update personal profile.

---

### 4.2 Hiring Organization

A Hiring Organization represents a company, startup, training institute, or educational institution that conducts technical assessments.

Responsibilities:
- Register the organization.
- Log in to the organization dashboard.
- Create and manage assessments.
- Add, edit, and delete questions.
- Generate and share assessment links.
- View candidate submissions.
- Review assessment results.
- Manage organization profile.

---

### 4.3 Administrator

The Administrator manages the overall TestGuru platform.

Responsibilities:
- Manage organizations.
- Manage candidates.
- Monitor assessments.
- View platform statistics.
- Handle reported issues.
- Manage system settings.

## 5. Functional Requirements

### Authentication
- Users shall be able to register and log in securely.
- The system shall support role-based authentication (Administrator, Hiring Organization, Candidate).
- The system shall allow users to reset their passwords.

### Hiring Organization
- Register and manage organization profile.
- Create, edit, publish, and delete assessments.
- Add, edit, and delete MCQ questions.
- Set assessment duration and passing criteria.
- Generate a unique assessment link.
- View candidate submissions and results.

### Candidate
- Register using the assessment link.
- Log in to access assigned assessments.
- Start and complete assessments.
- Submit responses before the timer expires.
- View assessment status.
- View results (if enabled by the organization).

### Administrator
- Manage organizations.
- Manage candidates.
- Monitor assessments.
- View platform statistics.
- Manage reported issues.

### Assessment Management
- Support multiple assessments.
- Automatically calculate scores for MCQ questions.
- Store assessment history.

## 6. Non-Functional Requirements

- The application shall provide a responsive user interface.
- User passwords shall be securely encrypted.
- The system shall support multiple users simultaneously.
- The platform shall provide role-based access control.
- The application shall be easy to maintain and extend.
- The system shall provide reliable performance and availability.
- The platform shall validate user input to prevent invalid data.
- The application shall maintain data integrity and consistency.

## 7. Assumptions

- Users have a stable internet connection.
- Users access the platform through a modern web browser.
- Organizations are responsible for creating valid assessments.
- Candidates use their own devices to take assessments.

## 8. Future Enhancements

- Coding assessments
- AI-based proctoring
- Video monitoring
- Email notifications
- Certificates
- Analytics dashboard
- Question bank import/export
- Mobile application
