# Use Case Model List (UCML)

---

## UC-01: Successful User Login

Actor: Registered User  
Frequency: 80%

### Preconditions
- User account exists
- User provides valid email and password

### Main Flow
- User submits valid credentials
- System authenticates user
- System returns authentication token

**Mapped JMeter Test:** `PracticeTestAutomation_Login_Test.jmx`

---

## UC-02: Manage Interviews

**Actor:** Recruiter / Admin  
**Frequency:** 40%  

### Preconditions
- User is authenticated (valid JWT token available)
- User has sufficient privileges to manage interviews

### Description / Main Flow
- User views published and unpublished interviews
- User creates a new interview
- User updates interview information
- User retrieves interview details by ID
- User deletes the interview

**Mapped JMeter Test:** `PracticeTestAutomation_InterviewOps_Test.jmx`

---