PROBLEM STATEMENT: 
        Healthcare facilities feel difficult to handle large volumes of information, including personal details, medical history, appointments, and treatment plans.
Manual handling of such information can lead to errors, inefficiencies, and data loss and also a lot of manpower.
A digital Patient Management System can significantly improve the accuracy, efficiency, and make it easier to access and work with, also can engage the staff in other activities. 

OBJECTIVES :

● To create a C++ application such that Healthcare providers should be able to easily track, store, and access their patients’ details 
● To book appointments for patients and can check the doctor’s availability 
● To make it work such that it keeps track of payment details. 
● To add the feature of validation of Insurance eligibility when a patient checks out

 INHERITANCE:

  Inheritance is a fundamental concept in object-oriented programming where a new class (called a subclass or derived class) is created based on an existing class (called a superclass or base class). 
  Here we have used HIERARCHICAL Inheritance and SINGLE Inheritance
● Hierarchical Inheritance refers to the two or many classes derived from a Single Base class 
● Single Inheritance refers to a Single derived class derived from a Single Base class.
 Hierarchical inheritance is used to extract and access the basic details of the patient like name, bp level, weight etc. From the patient class (base class) to its derived classes outpatient & inpatient (derived classes).
 Single Inheritance is used to get the details of Bill amount from the Billing (Base class) for the processing of Insurance and deducting the amount using the Insurance class (Derived class of Billing). 


POLYMORPHISM: 

 Run time polymorphism is implemented in this application (function overriding). The display () function is used to implement the run time polymorphism.
 The display () function in the patient class (base class) is used to display the basic details of the patient, display () function in the inpatient is used to display the details of inpatient, 
 display () function in the outpatient is used to display the details of outpatient. 


FILE CONCEPTS: 

Files are used to get the details of doctors. We have used 6 files in which the information is already stored. The file contains the name of the doctor and the number of slots available for him/her for the day.
Each file represents one specialized department of the hospital.
The files used for this application are 
Cardiology 
Neurology 
Nephrology 
Oncology 
Radiology 
General Medicine

EXCEPTION HANDLING:

Exception handling in C++ is a mechanism that allows a program to deal with unexpected situations (exceptions) by using `try`, `catch`, and `throw` blocks to separate errorhandling code from regular code flow.
It provides a way to transfer control and error information to a predefined error handler, enabling the program to continue or safely terminate.
We have used many user defined exceptions each checking a particular condition. Exception handling is implemented in the following 
Choices 
Phone Number 
Weight 
BP level 
Date 

TEMPLATES : 

In C++, a template is a powerful feature that allows functions and classes to operate with generic types, enabling code reuse and flexibility.
There are two main types of templates: function templates and class templates. We have included function templates in this program.
A function template in C++ allows the creation of a single function definition that can work with different data types.
By using template parameters, it enables functions to be written in a generic manner, making them flexible and reusable for various types without the need for multiple definitions.
A function chkname() is defined as a template function, it gets any data type as parameters and further do the processes with the template parameter which is get as parameter




