# Automation Practice Tests

## Application Overview

Comprehensive test plan for the Automation Practice website (https://rahulshettyacademy.com/AutomationPractice/). This site provides practice scenarios for web automation testing. The plan covers user authentication (login) and interaction with form elements including radio button selections. The tests will verify proper login functionality and the ability to select radio button options on the page.

## Test Scenarios

### 1. Automation Practice Tests

**Seed:** `seed.spec.ts`

#### 1.1. Login and Select Radio Button

**File:** `tests/automation-practice/login-and-radio-button.spec.ts`

**Steps:**
  1. Navigate to the Automation Practice website at https://rahulshettyacademy.com/AutomationPractice/
    - expect: The page loads successfully
    - expect: The page title shows 'Practice Page'
    - expect: All page elements are visible
  2. Scroll down to locate the login form section on the page
    - expect: Login form becomes visible
    - expect: Login form contains email/username field
    - expect: Login form contains password field
    - expect: Login button is visible
  3. Enter valid credentials in the login form (username: practice, password: SuperSecurePassword)
    - expect: Email/username field accepts input
    - expect: Password field accepts input and masks the characters
    - expect: Text is properly entered in both fields
  4. Click the 'Login' button to submit the form
    - expect: The form submission is triggered
    - expect: A success/confirmation message appears or page navigates
    - expect: No error message is displayed
  5. Scroll to locate the radio button elements on the page (typically in a practice form section)
    - expect: Radio button group is visible
    - expect: Multiple radio button options are displayed
    - expect: Each radio button is clearly identifiable
  6. Click on the first radio button option to select it
    - expect: The radio button becomes selected (filled/checked state)
    - expect: Any previously selected radio button is deselected (if one existed)
    - expect: Visual indication shows the selection state
  7. Verify the radio button selection state by checking the element's properties
    - expect: The radio button is marked as checked/selected
    - expect: The element's value is properly set
    - expect: The selection persists on the page
  8. Click on a different radio button option to change the selection
    - expect: The previously selected radio button becomes deselected
    - expect: The new radio button becomes selected
    - expect: Only one radio button is selected at a time
  9. Verify the final radio button selection state
    - expect: The current radio button shows as selected
    - expect: The element attributes reflect the selected state
    - expect: The page maintains the selection

#### 1.2. Login with Invalid Credentials

**File:** `tests/automation-practice/login-invalid-credentials.spec.ts`

**Steps:**
  1. Navigate to the Automation Practice website
    - expect: The page loads successfully
  2. Locate the login form on the page
    - expect: Login form is visible with email and password fields
  3. Enter invalid credentials (username: invalid, password: wrongpassword)
    - expect: Text is entered in both username and password fields
  4. Click the Login button
    - expect: The form is submitted
    - expect: An error message appears indicating invalid credentials
    - expect: The user remains on the login page

#### 1.3. Verify Radio Button Mutual Exclusivity

**File:** `tests/automation-practice/radio-button-exclusivity.spec.ts`

**Steps:**
  1. Navigate to the Automation Practice website
    - expect: The page loads successfully
  2. Locate all radio button elements in the practice form
    - expect: All radio buttons are visible
    - expect: Radio buttons are part of the same group
  3. Click on the first radio button
    - expect: The first radio button is selected
    - expect: The selected state is visually indicated
  4. Click on the second radio button
    - expect: The second radio button is now selected
    - expect: The first radio button is automatically deselected
    - expect: Only one radio button in the group is selected
  5. Click on the third radio button (if available)
    - expect: The third radio button is now selected
    - expect: The second radio button is automatically deselected
    - expect: Radio buttons maintain mutual exclusivity
  6. Verify no radio buttons remain selected if clicking outside the group
    - expect: The page maintains the radio button state as designed

#### 1.4. Radio Button Selection After Login

**File:** `tests/automation-practice/radio-button-after-login.spec.ts`

**Steps:**
  1. Navigate to the Automation Practice website
    - expect: The page loads successfully
  2. Complete the login process with valid credentials
    - expect: Login is successful
    - expect: User is authenticated
  3. Scroll to the radio button section after successful login
    - expect: Radio buttons remain available after login
    - expect: Radio button elements are still interactive
  4. Select multiple radio buttons sequentially and verify each selection
    - expect: Each radio button click is registered
    - expect: Selection state changes are reflected immediately
    - expect: Only one radio button remains selected in the group

#### 1.5. Login Form Validation - Empty Fields

**File:** `tests/automation-practice/login-empty-fields.spec.ts`

**Steps:**
  1. Navigate to the Automation Practice website
    - expect: The page loads successfully
  2. Locate the login form without entering any credentials
    - expect: Login form fields are empty
  3. Click the Login button without entering any data
    - expect: Form validation is triggered
    - expect: Error message or validation feedback appears
    - expect: Login is not processed
  4. Verify validation messages for both empty fields
    - expect: Appropriate validation messages are displayed
    - expect: User is informed about required fields
