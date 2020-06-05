---
title: Verwenden von Varianz in Schnittstellen für generische Sammlungen
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: b762ce42215f9b24371313446637e95962677bfb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375640"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="7efa1-102">Using Variance in Interfaces for Generic Collections (Visual Basic) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="7efa1-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>

<span data-ttu-id="7efa1-103">Eine kovariante Schnittstelle ermöglicht den zugehörigen Methoden, mehr abgeleitete Typen zurückzugeben, als in der Schnittstelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7efa1-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="7efa1-104">Eine kontravariante Schnittstelle ermöglicht den zugehörigen Methoden, Parameter von weniger abgeleiteten Typen anzunehmen, als in der Schnittstelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7efa1-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>

<span data-ttu-id="7efa1-105">In .NET Framework 4 wurden mehrere vorhandene Schnittstellen kovariant und kontravariant.</span><span class="sxs-lookup"><span data-stu-id="7efa1-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="7efa1-106">Dazu gehören <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="7efa1-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="7efa1-107">Dadurch können Sie Methoden wiederverwenden, die mit generischen Auflistungen von Basistypen für Sammlungen von abgeleiteten Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7efa1-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>

<span data-ttu-id="7efa1-108">Eine Liste der variant-Schnittstellen im .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="7efa1-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md).</span></span>

## <a name="converting-generic-collections"></a><span data-ttu-id="7efa1-109">Konvertieren von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="7efa1-109">Converting Generic Collections</span></span>

<span data-ttu-id="7efa1-110">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7efa1-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7efa1-111">Die `PrintFullName`-Methode akzeptiert eine Auflistung vom Typ `IEnumerable(Of Person)` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="7efa1-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="7efa1-112">Sie können dies jedoch für eine Auflistung des Typs `IEnumerable(Of Person)` wiederverwenden, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="7efa1-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a><span data-ttu-id="7efa1-113">Vergleichen von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="7efa1-113">Comparing Generic Collections</span></span>

<span data-ttu-id="7efa1-114">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kontravarianz in der <xref:System.Collections.Generic.IComparer%601>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7efa1-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="7efa1-115">Die `PersonComparer`-Klasse implementiert die `IComparer(Of Person)`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7efa1-115">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="7efa1-116">Sie können diese Klasse jedoch zum Vergleich einer Sequenz von Objekten des Typs `Employee` wiederverwenden, da `Employee``Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="7efa1-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class
' The custom comparer for the Person type
' with standard implementations of Equals()
' and GetHashCode() methods.
Class PersonComparer
    Implements IEqualityComparer(Of Person)

    Public Function Equals1(
        ByVal x As Person,
        ByVal y As Person) As Boolean _
        Implements IEqualityComparer(Of Person).Equals

        If x Is y Then Return True
        If x Is Nothing OrElse y Is Nothing Then Return False
        Return (x.FirstName = y.FirstName) AndAlso
            (x.LastName = y.LastName)
    End Function
    Public Function GetHashCode1(
        ByVal person As Person) As Integer _
        Implements IEqualityComparer(Of Person).GetHashCode

        If person Is Nothing Then Return 0
        Dim hashFirstName =
            If(person.FirstName Is Nothing,
            0, person.FirstName.GetHashCode())
        Dim hashLastName = person.LastName.GetHashCode()
        Return hashFirstName Xor hashLastName
    End Function
End Class

Sub Main()
    Dim employees = New List(Of Employee) From {
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}
    }

    ' You can pass PersonComparer,
    ' which implements IEqualityComparer(Of Person),
    ' although the method expects IEqualityComparer(Of Employee)

    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())

    For Each employee In noduplicates
        Console.WriteLine(employee.FirstName & " " & employee.LastName)
    Next
End Sub
```

## <a name="see-also"></a><span data-ttu-id="7efa1-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7efa1-117">See also</span></span>

- [<span data-ttu-id="7efa1-118">Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="7efa1-118">Variance in Generic Interfaces (Visual Basic)</span></span>](variance-in-generic-interfaces.md)
