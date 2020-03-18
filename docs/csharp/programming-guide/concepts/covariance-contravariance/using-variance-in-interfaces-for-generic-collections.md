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
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a>Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#)
Eine kovariante Schnittstelle ermöglicht den zugehörigen Methoden, mehr abgeleitete Typen zurückzugeben, als in der Schnittstelle angegeben sind. Eine kontravariante Schnittstelle ermöglicht den zugehörigen Methoden, Parameter von weniger abgeleiteten Typen anzunehmen, als in der Schnittstelle angegeben sind.  
  
 In .NET Framework 4 wurden mehrere vorhandene Schnittstellen kovariant und kontravariant. Dazu gehören <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IComparable%601>. Dadurch können Sie Methoden wiederverwenden, die mit generischen Auflistungen von Basistypen für Sammlungen von abgeleiteten Typen verwendet werden.  
  
 Eine Liste von varianten Schnittstellen in .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (C#)](./variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Konvertieren von generischen Auflistungen  
 Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle. Die `PrintFullName`-Methode akzeptiert eine Auflistung vom Typ `IEnumerable<Person>` als Parameter. Sie können dies jedoch für eine Auflistung des Typs `IEnumerable<Employee>` wiederverwenden, da `Employee``Person` erbt.  
  
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
  
## <a name="comparing-generic-collections"></a>Vergleichen von generischen Auflistungen  
 Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kontravarianz in der <xref:System.Collections.Generic.IComparer%601>-Schnittstelle. Die `PersonComparer`-Klasse implementiert die `IComparer<Person>`-Schnittstelle. Sie können diese Klasse jedoch zum Vergleich einer Sequenz von Objekten des Typs `Employee` wiederverwenden, da `Employee``Person` erbt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Varianz in generischen Schnittstellen](./variance-in-generic-interfaces.md)
