
# Apex Collections Practice 🚀

This repository contains practical examples of **Apex Collections** used in Salesforce.

It is created for beginners to understand how collections work and how they are used in real scenarios like Triggers.

---

## 📌 Collections in Apex

Apex provides 3 types of collections:

* **List** → Ordered collection (duplicates allowed)
* **Set** → Unordered collection (no duplicates)
* **Map** → Key-value pair collection

---

## 🔹 Current Topic: List

### ✔ What is List?

List is used to store multiple values in a single variable.
It maintains order and allows duplicate values.

---

## 💻 Example

```apex
public class Collection {
    
    public static void handleListCollections(){
        
        List<String> myFavBooks = new List<String>{'The MOnk','Osho Mount','The Desire Of Enviournment'};
        List<integer> myFavNumbers = new List<integer>{1,2,3,4};
        List<Boolean> myThoughts = new List<Boolean>{True,False};
        List<String>  myFavDrinks = new List<String>();
        
      Account accRec = new Account();
      List<Account> AccountRec = new List<Account>{accRec};
        
     //add     
          myFavBooks.add('The Lion');
          myFavNumbers.add(1);        
        System.debug('My Fav Numbers are:' + myFavNumbers);  //1,2,3,4,1
        
      //get          
         System.debug('Books in 1st Index is :' + myFavBooks.get(1));      //Osho Mount
          
      //Size  
          System.debug(' My Books Count is :' + myFavBooks.Size());
        
      //isEmpty 
          System.debug(' Is my List is empty:' + myFavBooks.isEmpty());    //false
          System.debug(' Is my List is empty :' + myFavDrinks.isEmpty());  // true
        
          System.debug(myFavBooks.size() == 0);
          System.debug(myFavDrinks.size() == 0);
        
      //clear
         system.debug('my Thoughts Before:' + myThoughts);
         myThoughts.clear();
         system.debug('my Thoughts After :' + myThoughts);
       
      //IndexOf
        System.debug(' Osho Monk at:' + myFavBooks.indexOf('Osho Mount'));    // 1          
        System.debug(' Osho Monk at:' + myFavBooks.indexOf('Osho Mountt'));   // -1  wrong Put 
        
      //Contains
        String yourFavBook = 'The Four Aggrement';
        System.debug(myFavBooks.contains(yourFavBook));   // False
        
        if(myFavBooks.contains(yourFavBook)){
            System.debug('Yup We Have Common Book');   
        }
        else{
            System.debug('Can i Borrow Your Book');    // Can i Borrow Your Book
        }         
    } 
}

✔ Real Use Case (Important 🔥)
List<Account> accList = [SELECT Id, Name FROM Account];

for(Account acc : accList){
    System.debug(acc.Name);
}

👉 SOQL always returns List
👉 Trigger.new also gives List of records

---
🔹 Set ✔
✔ What is Set?

Set is used to store unique values in a single variable.
It automatically removes duplicate values and does not maintain insertion order.

✔ Why use Set?
To remove duplicate data
To check existence quickly (contains)
To improve performance in bulk operations

✔ Common Methods
currencies.add('CAD');         // Add value
currencies.remove('USD');      // Remove value
currencies.contains('INR');    // Check existence
currencies.size();             // Total elements
currencies.isEmpty();          // Check empty
currencies.clear();            // Remove all


💻 Example
 public static void handleSetCollections(){
        
        Set<String> myPaintings = new Set<String>();
        Set<String> myCurrencies = new Set<String>{'AED','INR','USD','CAD','INR'};   // USD,AED,INR,CAD
        System.debug(myCurrencies);
        
        System.debug(myCurrencies.add('SGD'));     // AED,INR,USD,SGD
        System.debug(myCurrencies.remove('USD')); 
     // myCurrencies.get(0);                          this Method not Avilable Because It is Unorderd So 
     // myCurrencies.indexOf('CAD');                  Same for This Method Also
        System.debug(myCurrencies.contains('MRU'));
        System.debug(myCurrencies.size());          // 4
    }

✔ Real Use Case (Important)
List<String> data = new List<String>{'A','B','A','C'};

Set<String> uniqueData = new Set<String>(data);

System.debug(uniqueData); // A, B, C

👉 Used to remove duplicates from List


🔹 Map ✔
✔ What is Map?

Map is used to store data in key-value pair format.
Each key is unique and is used to retrieve its corresponding value.

✔ Why use Map?
Fast data access using key
Avoid nested loops (performance boost)
Used heavily in Triggers

✔ Common Methods
students.put(3, 'Neha');        // Add
students.get(1);                // Get value
students.containsKey(2);        // Check key
students.remove(2);             // Remove
students.size();                // Count
students.isEmpty();             // Check empty
students.keySet();              // All keys
students.values();              // All values
students.clear();               // Remove all


💻 Example
public static void handleMapCollections(){
       Map<String,String> employeeDetails = New Map<String,String>();
        
        System.debug(employeeDetails.isEmpty());      // True
        
       employeeDetails.put('EMP1002','Sheldon Cooper');
       employeeDetails.put('EMP1003','Camroon Green');
       employeeDetails.put('EMP1004','Josh Buttler');
       employeeDetails.put('EMP1005','Brendum Makalum');
       employeeDetails.put('EMP1006','Devil Jame'); 
        
         System.debug(employeeDetails.isEmpty());    //false
        
        System.debug('All the Employee Id are :' + employeeDetails.KeySet());   //use for Sagrigate VAlues
        System.debug('All the Employee Id are :' + employeeDetails.values());    //
        System.debug('Total Of Employees is :' + employeeDetails.Size());        
    }

✔ Real Use Case (Very Important 🔥)
List<Account> accList = [SELECT Id, Name FROM Account];

Map<Id, Account> accMap = new Map<Id, Account>(accList);

Account acc = accMap.get(someId);

👉 Direct record access without loop
👉 Used in almost every Trigger



🎯 Why this Repository?
To understand List, Set, and Map step by step
To prepare for Salesforce Developer interviews
To build strong fundamentals of Apex

🚀 Next Steps
More Set & Map use cases
Advanced collection problems
Trigger-based real-world scenarios

👨‍💻 Author
Learning Salesforce and improving Apex skills with practical examples.

⭐ Star this repo if you find it useful!
---

