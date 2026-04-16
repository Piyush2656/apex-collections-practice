
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
---

## 🎯 Why this Repository?

* To understand List, Set, and Map step by step
* To prepare for Salesforce Developer interviews
* To build strong fundamentals of Apex

---

## 🚀 Upcoming

* Set collection examples
* Map collection examples
* Trigger-based real use cases

---

## 👨‍💻 Author

Learning Salesforce and improving Apex skills with daily practice.

---

⭐ Star this repo if you find it useful!
