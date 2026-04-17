
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

## 🔹 List ✔

### ✔ What is List?

List is used to store multiple values in a single variable.
It maintains order and allows duplicate values.

---

### ✔ Example

```apex
public class Collection {

    public static void handleListCollections(){

        List<String> myFavBooks = new List<String>{
            'The Monk','Osho Mount','The Desire Of Environment'
        };

        List<Integer> myFavNumbers = new List<Integer>{1,2,3,4};
        List<Boolean> myThoughts = new List<Boolean>{true,false};
        List<String> myFavDrinks = new List<String>();

        Account accRec = new Account();
        List<Account> accountRec = new List<Account>{accRec};

        // Add
        myFavBooks.add('The Lion');
        myFavNumbers.add(1);

        // Get
        System.debug(myFavBooks.get(1));

        // Size
        System.debug(myFavBooks.size());

        // isEmpty
        System.debug(myFavDrinks.isEmpty());

        // Clear
        myThoughts.clear();

        // IndexOf
        System.debug(myFavBooks.indexOf('Osho Mount'));

        // Contains
        String yourFavBook = 'The Four Agreement';
        System.debug(myFavBooks.contains(yourFavBook));
    }
}
```

---

### ✔ Real Use Case (Important 🔥)

```apex
List<Account> accList = [SELECT Id, Name FROM Account];

for(Account acc : accList){
    System.debug(acc.Name);
}
```

👉 SOQL always returns List
👉 Trigger.new also returns List

---

## 🔹 Set ✔

### ✔ What is Set?

Set is used to store unique values in a single variable.
It removes duplicate values and does not maintain order.

---

### ✔ Example

```apex
public static void handleSetCollections(){

    Set<String> myCurrencies = new Set<String>{
        'AED','INR','USD','CAD','INR'
    };

    System.debug(myCurrencies);

    myCurrencies.add('SGD');
    myCurrencies.remove('USD');

    System.debug(myCurrencies.contains('INR'));
    System.debug(myCurrencies.size());
}
```

---

### ✔ Common Methods

* add()
* remove()
* contains()
* size()
* isEmpty()
* clear()

---

### ✔ Real Use Case (Important 🔥)

```apex
List<String> data = new List<String>{'A','B','A','C'};

Set<String> uniqueData = new Set<String>(data);

System.debug(uniqueData);
```

👉 Used to remove duplicates from List

---

## 🔹 Map ✔

### ✔ What is Map?

Map is used to store data in key-value pair format.
Each key is unique and used to retrieve its value.

---

### ✔ Example

```apex
public static void handleMapCollections(){

    Map<String,String> employeeDetails = new Map<String,String>();

    employeeDetails.put('EMP1002','Sheldon Cooper');
    employeeDetails.put('EMP1003','Camroon Green');
    employeeDetails.put('EMP1004','Josh Buttler');

    System.debug(employeeDetails.get('EMP1002'));
    System.debug(employeeDetails.keySet());
    System.debug(employeeDetails.values());
    System.debug(employeeDetails.size());
}
```

---

### ✔ Common Methods

* put()
* get()
* containsKey()
* remove()
* size()
* isEmpty()
* keySet()
* values()
* clear()

---

### ✔ Real Use Case (Very Important 🔥)

```apex
List<Account> accList = [SELECT Id, Name FROM Account];

Map<Id, Account> accMap = new Map<Id, Account>(accList);

Account acc = accMap.get(someId);
```

👉 Direct access without loop
👉 Used in almost every Trigger

---

## 🎯 Why this Repository?

* To understand List, Set, and Map step by step
* To prepare for Salesforce Developer interviews
* To build strong fundamentals of Apex

---

## 🚀 Next Steps

* More Set & Map use cases
* Advanced collection problems
* Trigger-based real-world scenarios

---

## 👨‍💻 Author

Learning Salesforce and improving Apex skills with practical examples.

---

⭐ Star this repo if you find it useful!
