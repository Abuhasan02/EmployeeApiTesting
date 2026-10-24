## Employee REST API Testing

API testing project for the Employee REST API using **Postman** and **Newman**.
Covers login, create, read, update, delete, and query parameter scenarios
with both positive and negative test cases.

## Table of Contents
- [Tools Used](#tools-used)
- [Project Structure](#project-structure)
- [Test Scenarios](#test-scenarios)
- [API Documentation](#api-documentation)
- [How to Run](#how-to-run)
- [Newman Report](#newman-report)
- [Bug Reports](#bug-reports)
- [Author](#author)

## Tools Used
- Postman (collection, environment, test scripts)
- Newman (command line runner)
- newman-reporter-htmlextra (HTML report)
- Jira (bug tracking)
- Git and GitHub

## Project Structure
```
EmployeeApiTesting/
├── Reports/                      # Newman HTML report
├── screenshots/                  # Evidence screenshots
├── SqalogyB3TestCollection.postman_collection.json
├── SQALOGYB3TestEnv.postman_environment.json
├── package.json
└── README.md
```

## Test Scenarios
| # | Scenario | Type |
|---|---|---|
| 1 | Login with valid credentials | Positive |
| 2 | Login with invalid credentials | Negative |
| 3 | Create 5 employees with random data | Positive |
| 4 | Get employee by ID and verify department | Positive |
| 5 | Update employee phone and position | Positive |
| 6 | Delete an employee and verify deletion | Positive |
| 7 | Get all employees and verify count | Positive |
| 8 | Get employees with query params (phone, email) | Positive |

**Total test cases:** [40]  |  **Passed:** [35]  |  **Failed:** [5]

## API Documentation
Published Postman documentation: [Employee API Documentation](https://documenter.getpostman.com/view/10019293/2sBYHUTfLK)
## How to Run
1. Clone the repository
   ```
   git clone https://github.com/Abuhasan02/EmployeeApiTesting.git
   cd EmployeeApiTesting
   ```
2. Install dependencies
   ```
   npm install
   ```
3. Run the collection
   ```
   npx newman run SqalogyB3TestCollection.postman_collection.json -e SQALOGYB3TestEnv.postman_environment.json -r htmlextra
   ```
## Git Workflow

Commands used to publish this project:

```bash
npm init -y
```
```bash
npm i newman
```
```bash
npx newman run [collection] -e [environment]
```
```bash
npm i newman-reporter-htmlextra
```
## Newman Report
(<img width="565" height="592" alt="image" src="https://github.com/user-attachments/assets/b46e40e1-1d4b-4d66-9dd3-52475ee0b197" />
)
(<img width="851" height="570" alt="image" src="https://github.com/user-attachments/assets/28a3350e-04f0-407b-8f3f-3d7587853d11" />
)

## Bug Reports
| Bug ID | Jira ID | Endpoint | Summary | Severity |
|---|---|---|---|---|
| BUG-001 | EAT-1 | POST /api/employees | Accepts invalid email format | Medium |
| BUG-002 | EAT-2 | POST /api/employees | Accepts a negative salary | Medium |
| BUG-003 | EAT-3 | POST /api/employees | Accepts a number for position | Medium |
| BUG-004 | EAT-4 | POST /api/employees | Accepts a number for lastName | Medium |
| BUG-005 | EAT-5 | PATCH /api/employees/{id} | Accepts salary of 0 | Medium |

Full bug report: [API_Bug_Report.xlsx](BugReport/API_Bug_Report.xlsx)

## Author
Abu Hasan Siddique
