### Rest Booking API Testing with Postman & Newman
This project provides an example of utilizing Postman for API testing, including a set of tests to verify different API endpoints.

### **Features**

- Tests for GET, POST, PUT, DELETE requests
- Collection of tests covering different API endpoints
- Environment setup for easy switching between environments
- Pre-request scripts for data setup
- Test scripts for assertions and validations

## API Documentation:
- https://documenter.getpostman.com/view/13082503/2sA2xmUAJ1
  
### **Technology used:**
- Postman
- Newman

### **Prerequisite:**
- Node Js
- Newman
- Newman Html Report Library

### **Installation**

1. Postman: If you haven't already, [download and install Postman.](https://www.postman.com/downloads/)
2. Clone the repository:

 ```console 
  git clone https://github.com/MdTajwarAliRumman/MdTajwarAliRumman-Automation-Testing-of-the-Rest-Booking-API-and-Newman-Report.git
```
3. Import the Postman collection:
    - Open Postman.
    - Click on the Import button.
    - Select the file from the repository.
4. Import the Postman environment:
    - In Postman, click on the gear icon in the top right corner.
    - Select **Import** and choose the file.
5. Newman and Report Installation Process:
    - Newman Install Command:
     ```console 
      npm install -g newman
    ```
    - Newman Html Report Install Command:
     ```console 
      npm install -g newman-reporter-htmlextra
    ```
### **Usage**
1. Select Environment:
    -   In Postman, select the appropriate environment (e.g., Development, Production) from the top-right dropdown.
3. Run Collection:
    -   Select the imported collection from the Collections sidebar.
    -   Click on the Runner button to open the collection runner.
    -   Select the desired environment.
    -   Click Start Test to run the collection.
8. View Results:
    -   Once the tests are complete, view the results in the Runner tab.
    -   Detailed test results can be viewed for each request.
  
## **Testing**

## Test Case Scenarios:

## _**1. Create New Booking**_

### Request URL: https://restful-booker.herokuapp.com/booking/
### Request Method: POST
### Pre-request Script:

```console 
     var firstName = pm.variables.replaceIn("{{$randomFirstName}}")
     console.log(firstName)
     pm.environment.set("firstName", firstName)
     
     var lastName = pm.variables.replaceIn("{{$randomLastName}}")
     console.log(lastName)
     pm.environment.set("lastName", lastName)
     
     var totalPrice = pm.variables.replaceIn("{{$randomInt}}")
     pm.environment.set("totalPrice", totalPrice)
     console.log(totalPrice)
     
     var depositPaid = pm.variables.replaceIn("{{$randomBoolean}}")
     pm.environment.set("depositPaid", depositPaid)
     console.log(depositPaid)
     
     var additionalNeeds = pm.variables.replaceIn("{{$randomProduct}}")
     pm.environment.set("additionalNeeds", additionalNeeds)
     console.log(additionalNeeds)
     
     // date checkin
     const moment = require("moment")
     const today = moment()
     pm.environment.set("checkin", today.format("YYYY-MM-DD"))
     // date checkout
     pm.environment.set("checkout", today.add(5,'d').format("YYYY-MM-DD"))
     console.log(today.format("YYYY-MM-DD"))
     
     
     // future date example
     //pm.environment.set("checkin", today.add(5,"d").add(1,"M").format("YYYY-MM-DD"))
     
     // past date example
     //pm.environment.set("checkin", today.subtract(5,"d").subtract(1,"M").format("YYYY-MM-DD"))

 ```
