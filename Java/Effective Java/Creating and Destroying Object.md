## Item 1 : Consider using static factory instead of public constructor

 - Two way of getting instance of a class
	 -  Using Public Constructor
	 -  Using public static factory
 ```Java

// Public Constructor

 private Employee(int empId, String empName, String empSurname, String empEmail, String empPhone) {
        this.empId = empId;
        this.empName = empName;
        this.empSurname = empSurname;
        this.empEmail = empEmail;
        this.empPhone = empPhone;
    }

// Public static Factory
    public static Employee getInstance(int empId, String empName, String empSurname, String empEmail, String empPhone) {
        if(employee == null) {
            employee = new Employee(empId,empName,empSurname,empEmail,empPhone);
        }
        return employee;
    }
```

#### Advantages of using Public static factory methods instead of Constructor

1. Have Names : 