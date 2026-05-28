# gmail-compose-testing
Gmail Compose Functionality Testing

This repository contains manual test cases for Gmail Compose functionality as part of the Incubyte QA assessment.

**Contents-**
Traditional Style Test Cases
BDD Style Test Cases
Positive and Negative Scenarios
Tested Functionality
Compose Email
Subject Validation
Email Body Validation
Send Email
Draft Functionality
Error Handling
Attachment Support
Tools Used
Microsoft Excel
Gmail Web Application

**BDD Styled/**
Feature: Gmail Compose Functionality Testing

Scenario: Successfully send email with valid details
Given the user is logged into Gmail
When the user clicks on Compose button
And enters a valid recipient email
And enters subject as "Incubyte"
And enters body as "QA test for Incubyte"
And clicks on Send button
Then the email should be sent successfully

Scenario: Verify compose window opens
Given the user is logged into Gmail
When the user clicks on Compose button
Then compose popup should open successfully

Scenario: Verify subject field accepts input
Given compose popup is open
When the user enters "Incubyte" in subject field
Then the subject should be displayed correctly

Scenario: Verify body field accepts input
Given compose popup is open
When the user enters "QA test for Incubyte" in body field
Then the body content should be displayed correctly

Scenario: Verify sending email without recipient
Given compose popup is open
When the user enters subject and body
And clicks on Send button without recipient
Then an error message should appear

Scenario: Verify invalid email validation
Given compose popup is open
When the user enters invalid email format
Then validation error should be displayed

Scenario: Verify auto-save draft functionality
Given compose popup is open
When the user types email content
And closes the compose popup
Then the draft should be auto-saved

Scenario: Verify sending email without subject
Given compose popup is open
When the user enters recipient and body only
And clicks Send
Then warning popup should appear or email should send after confirmation

Scenario: Verify attachment functionality
Given compose popup is open
When the user clicks attachment icon
Then file upload window should open

Scenario: Verify internet failure during sending email
Given compose popup is open
When internet connection is disconnected
And user clicks Send
Then proper failure message should appear
