Quiz Practice - Laptop Rental
=============================

Criteria
--------
1.	Abstract Class 

Design at least three classes, consisting of one abstract class and two concrete class. Abstract class consists of all common attributes and behaviour that both of the concrete class had. Concrete class consist of specific attribute and behaviour that is not common between the concrete classes.

2.	Encapsulation 

Attributes of the class must be encapsulated in order to prevent illegal direct access, and can only be accessed using accessor and mutator that may perform validation before accessing the encapsulated attribute.

3.	Inheritance 

Concrete classes must inherit all attributes and behaviours from the abstract class.

4.	Polymorphism 

Concrete class may override behaviour inherited from abstract class according to their specific implementation.

Case Description
----------------

Laptop Rental is a traditional laptop rental store that has been around for quite some time in West Jakarta. In their business, the owners of Laptop Rental often find it difficult to manage their many laptops. Therefore, the owners of Laptop Rental have asked you as a prospective assistant to help them create a simple program to manage all of their laptops effectively using the Java programming language.

Menu
----

At the beginning of the program execution, the program will display 6 menus, which are:

1. Insert Laptop
   
2. View Laptop
   
3. Borrow Laptop
   
4. Repair Laptop
   
5. Delete Laptop
   
6. Exit

Insert Laptop
-------------

If the user chooses menu 1 "Insert Laptop", then:

The program will show 2 menus, which are:

1. Gaming Laptop
   
2. Office Laptop

After the user choose either menu 1 "Gaming Laptop" or 2 "Office Laptop", the program will ask the user to input the details, which consists of:

1. Name, which length must be between 4 and 30 characters (inclusive) and every word must be start with capital character.

2. Production Year, which must be between 2000 and 2024 (inclusive).

3. If the user chooses "Laptop Gaming", then:

- Laptop Type, which must be "Gaming" (case sensitive).\
- Laptop GPU Health, which must be more than 90 (inclusive).\
- Generate ID, which is obtained from a string starting with "GA" and followed by three random digits. Every ID must be unique.\

4. If the user chooses "Laptop Office", then:

- Laptop Type, which must be "Office" (case sensitive).\
- Laptop Hardware Health, which must be more than 80 (inclusive).\
- Generate ID, which is obtained from a string starting with "OF" and followed by three random digits. Every ID must be unique.\

5. Add the data to Java Collection and display a message.

View Laptop
-----------

If the user chooses menu 2 "View Laptop", then:

If the list is empty, then display the message "Gaming Laptop is empty" and "Office Laptop is empty". Otherwise, display all data in the list based on laptiop type.

Borrow Laptop
-------------

If the user chooses menu 3 "Borrow Laptop", then:

- Show all data in the list based on laptop type, validate the "Laptop GPU Health" or "Laptop Hardware Health" must be more than 25 (inclusive).\
- Then, the program will ask the user to input the laptop ID.\
- If laptop ID was not exists, then display the message "Laptop not found!"\
- Otherwise, borrow is an abstract function that depends on the child.\
- If the type of chooses ID is Gaming, so borrow will decrease the "Laptop GPU Health" by 15.\
- If the type of chooses ID is Office, so borrow will decrease the "Laptop Hardware Health" by 10.\
- Then, display the success message.\

Repair Laptop
-------------

If the user chooses menu 4 "Repair Laptop", then:

- Show all data in the list based on laptop type, validate the "Laptop GPU Health" or "Laptop Hardware Health" must be less than 25 (exclusive).\
- Then, the program will ask the user to input the laptop ID.\
- If laptop ID was not exists, then display the message "Laptop not found!"\
- Otherwise, repair is an abstract function that depends on the child.\
- If the type of chooses ID is Gaming, so borrow will decrease the "Laptop GPU Health" by 60.\
- If the type of chooses ID is Office, so borrow will decrease the "Laptop Hardware Health" by 70.\
- Then, display the success message.\

Delete Laptop
-------------

If the user chooses menu 5 "Delete Laptop", then:

- Show all data in the list based on laptop type.\
- Then, the program will ask the user to input the laptop ID.\
- If laptop ID was not exists, then display the message "Laptop not found!"\
- Otherwise, delete the laptop inputted ID from the list and display the success message.\

Exit
----

If the user chooses menu 6 "Exit", then the program will stop the execution.