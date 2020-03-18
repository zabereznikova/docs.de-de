---
title: Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#)
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: b891ccde93e18baf5d5e814911666e9c6268e009
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169739"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="81abf-102">Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#)</span><span class="sxs-lookup"><span data-stu-id="81abf-102">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="81abf-103">Eine kovariante Schnittstelle ermöglicht den zugehörigen Methoden, mehr abgeleitete Typen zurückzugeben, als in der Schnittstelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="81abf-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="81abf-104">Eine kontravariante Schnittstelle ermöglicht den zugehörigen Methoden, Parameter von weniger abgeleiteten Typen anzunehmen, als in der Schnittstelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="81abf-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="81abf-105">In .NET Framework 4 wurden mehrere vorhandene Schnittstellen kovariant und kontravariant.</span><span class="sxs-lookup"><span data-stu-id="81abf-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="81abf-106">Dazu gehören <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="81abf-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="81abf-107">Dadurch können Sie Methoden wiederverwenden, die mit generischen Auflistungen von Basistypen für Sammlungen von abgeleiteten Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81abf-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="81abf-108">Eine Liste von varianten Schnittstellen in .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="81abf-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="81abf-109">Konvertieren von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="81abf-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="81abf-110">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="81abf-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="81abf-111">Die `PrintFullName`-Methode akzeptiert eine Auflistung vom Typ `IEnumerable<Person>` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="81abf-111">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="81abf-112">Sie können dies jedoch für eine Auflistung des Typs `IEnumerable<Employee>` wiederverwenden, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="81abf-112">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="81abf-113">Vergleichen von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="81abf-113">Comparing Generic Collections</span></span>  
 <span data-ttu-id="81abf-114">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kontravarianz in der <xref:System.Collections.Generic.IComparer%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="81abf-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="81abf-115">Die `PersonComparer`-Klasse implementiert die `IComparer<Person>`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="81abf-115">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="81abf-116">Sie können diese Klasse jedoch zum Vergleich einer Sequenz von Objekten des Typs `Employee` wiederverwenden, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="81abf-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="81abf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81abf-117">See also</span></span>

- [<span data-ttu-id="81abf-118">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="81abf-118">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
