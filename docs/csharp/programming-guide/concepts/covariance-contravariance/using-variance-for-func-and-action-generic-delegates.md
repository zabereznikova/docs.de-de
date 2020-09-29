---
title: Verwenden von Varianz für die generischen Delegaten Func und Action (C#)
description: Hier erfahren Sie mehr über die Verwendung von Kovarianz und Kontravarianz in den generischen Delegaten „Func“ und „Action“, um Ihnen mehr Flexibilität im Code zu bieten.
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 613470d7870aa6a917d19904a92e56f0e61f1ed9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176343"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="ca93f-103">Verwenden von Varianz für die generischen Delegaten Func und Action (C#)</span><span class="sxs-lookup"><span data-stu-id="ca93f-103">Using Variance for Func and Action Generic Delegates (C#)</span></span>

<span data-ttu-id="ca93f-104">Diese Beispiele veranschaulichen, wie Sie Kovarianz und Kontravarianz in den generischen Delegaten `Func` und `Action` verwenden, um die Wiederverwendung von Methoden zu ermöglichen und mehr Flexibilität in Ihrem Code zu bieten.</span><span class="sxs-lookup"><span data-stu-id="ca93f-104">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="ca93f-105">Weitere Informationen zu Ko- und Kontravarianz finden Sie unter [Varianz bei Delegaten (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="ca93f-105">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="ca93f-106">Verwendung von Delegaten mit kovarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="ca93f-106">Using Delegates with Covariant Type Parameters</span></span>  

 <span data-ttu-id="ca93f-107">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in generischen `Func`-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="ca93f-107">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="ca93f-108">Die Methode `FindByTitle` nimmt einen Parameter vom Typ `String` entgegen und gibt ein Objekt vom Typ `Employee` zurück.</span><span class="sxs-lookup"><span data-stu-id="ca93f-108">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="ca93f-109">Allerdings können Sie diese Methode dem Delegaten `Func<String, Person>` zuweisen, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="ca93f-109">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="ca93f-110">Verwendung von Delegaten mit kontravarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="ca93f-110">Using Delegates with Contravariant Type Parameters</span></span>  

 <span data-ttu-id="ca93f-111">Im folgenden Beispiel werden die Vorteile der Unterstützung von Kontravarianz in generischen `Action`-Delegaten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ca93f-111">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="ca93f-112">Die `AddToContacts`-Methode nimmt einen Parameter vom Typ `Person` entgegen.</span><span class="sxs-lookup"><span data-stu-id="ca93f-112">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="ca93f-113">Allerdings können Sie diese Methode dem Delegaten `Action<Employee>` zuweisen, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="ca93f-113">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca93f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca93f-114">See also</span></span>

- [<span data-ttu-id="ca93f-115">Kovarianz und Kontravarianz (C#)</span><span class="sxs-lookup"><span data-stu-id="ca93f-115">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="ca93f-116">Generics</span><span class="sxs-lookup"><span data-stu-id="ca93f-116">Generics</span></span>](../../../../standard/generics/index.md)
