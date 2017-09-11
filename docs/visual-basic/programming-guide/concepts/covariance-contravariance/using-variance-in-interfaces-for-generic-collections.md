---
title: "Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="1c33f-102">Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c33f-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>
<span data-ttu-id="1c33f-103">Eine kovariante Schnittstelle ermöglicht den zugehörigen Methoden, mehr abgeleitete Typen als die in der Schnittstelle zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c33f-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="1c33f-104">Eine kontravariante Schnittstelle ermöglicht den zugehörigen Methoden, Parameter von weniger stark abgeleiteten Typen als die angegebenen in der Schnittstelle zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="1c33f-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="1c33f-105">In .NET Framework 4 wurden mehrere vorhandene Schnittstellen kovariante und kontravariante.</span><span class="sxs-lookup"><span data-stu-id="1c33f-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="1c33f-106">Dazu gehören <xref:System.Collections.Generic.IEnumerable%601>und <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1c33f-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="1c33f-107">Dadurch können Sie Methoden wiederverwenden, die mit generischen Auflistungen von Basistypen für Sammlungen von abgeleiteten Typen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c33f-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="1c33f-108">Eine Liste der Varianten Schnittstellen in .NET Framework, finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="1c33f-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="1c33f-109">Konvertieren von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="1c33f-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="1c33f-110">Das folgende Beispiel veranschaulicht die Vorteile der Kovarianz-Unterstützung in der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1c33f-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="1c33f-111">Die `PrintFullName` -Methode akzeptiert eine Auflistung der `IEnumerable(Of Person)` Typ als Parameter.</span><span class="sxs-lookup"><span data-stu-id="1c33f-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="1c33f-112">Sie können jedoch wiederverwenden, es für eine Sammlung von der `IEnumerable(Of Person)` eingeben, da `Employee` erbt `Person`.</span><span class="sxs-lookup"><span data-stu-id="1c33f-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>  
  
<span data-ttu-id="1c33f-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="1c33f-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="comparing-generic-collections"></a><span data-ttu-id="1c33f-114">Vergleichen von generischen Auflistungen</span><span class="sxs-lookup"><span data-stu-id="1c33f-114">Comparing Generic Collections</span></span>  
 <span data-ttu-id="1c33f-115">Das folgende Beispiel veranschaulicht die Vorteile der Kontravarianz-Unterstützung in der <xref:System.Collections.Generic.IComparer%601>Schnittstelle.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="1c33f-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="1c33f-116">Die `PersonComparer`-Klasse implementiert die `IComparer(Of Person)`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1c33f-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="1c33f-117">Jedoch können Sie diese Klasse, um eine Sequenz von Objekten eines vergleichen Wiederverwenden der `Employee` eingeben, da `Employee` erbt `Person`.</span><span class="sxs-lookup"><span data-stu-id="1c33f-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```vb  
' Simple hierarhcy of classes.  
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
  
## <a name="see-also"></a><span data-ttu-id="1c33f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c33f-118">See Also</span></span>  
 [<span data-ttu-id="1c33f-119">Varianz in generischen Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c33f-119">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
