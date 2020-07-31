---
title: Verwenden von Varianz für die generischen Delegaten Func und Action (C#)
description: Hier erfahren Sie mehr über die Verwendung von Kovarianz und Kontravarianz in den generischen Delegaten „Func“ und „Action“, um Ihnen mehr Flexibilität im Code zu bieten.
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: d7174b0f734d10ab69d0936cb5ca4aa2f4fafdf7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105713"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a>Verwenden von Varianz für die generischen Delegaten Func und Action (C#)
Diese Beispiele veranschaulichen, wie Sie Kovarianz und Kontravarianz in den generischen Delegaten `Func` und `Action` verwenden, um die Wiederverwendung von Methoden zu ermöglichen und mehr Flexibilität in Ihrem Code zu bieten.  
  
 Weitere Informationen zu Ko- und Kontravarianz finden Sie unter [Varianz bei Delegaten (C#)](./variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Verwendung von Delegaten mit kovarianten Typparametern  
 Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in generischen `Func`-Delegaten. Die Methode `FindByTitle` nimmt einen Parameter vom Typ `String` entgegen und gibt ein Objekt vom Typ `Employee` zurück. Allerdings können Sie diese Methode dem Delegaten `Func<String, Person>` zuweisen, da `Employee``Person` erbt.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Verwendung von Delegaten mit kontravarianten Typparametern  
 Im folgenden Beispiel werden die Vorteile der Unterstützung von Kontravarianz in generischen `Action`-Delegaten veranschaulicht. Die `AddToContacts`-Methode nimmt einen Parameter vom Typ `Person` entgegen. Allerdings können Sie diese Methode dem Delegaten `Action<Employee>` zuweisen, da `Employee``Person` erbt.  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Kovarianz und Kontravarianz (C#)](./index.md)
- [Generics](../../../../standard/generics/index.md)
