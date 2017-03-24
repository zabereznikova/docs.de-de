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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)
Eine kovariante Schnittstelle ermöglicht den zugehörigen Methoden, mehr abgeleitete Typen als die in der Schnittstelle zurückzugeben. Eine kontravariante Schnittstelle ermöglicht den zugehörigen Methoden, Parameter von weniger stark abgeleiteten Typen als die angegebenen in der Schnittstelle zu akzeptieren.  
  
 In .NET Framework 4 wurden mehrere vorhandene Schnittstellen kovariante und kontravariante. Dazu gehören <xref:System.Collections.Generic.IEnumerable%601>und <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601> Dadurch können Sie Methoden wiederverwenden, die mit generischen Auflistungen von Basistypen für Sammlungen von abgeleiteten Typen ausgeführt werden.  
  
 Eine Liste der Varianten Schnittstellen in .NET Framework, finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Konvertieren von generischen Auflistungen  
 Das folgende Beispiel veranschaulicht die Vorteile der Kovarianz-Unterstützung in der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601> Die `PrintFullName` -Methode akzeptiert eine Auflistung der `IEnumerable(Of Person)` Typ als Parameter. Sie können jedoch wiederverwenden, es für eine Sammlung von der `IEnumerable(Of Person)` eingeben, da `Employee` erbt `Person`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="comparing-generic-collections"></a>Vergleichen von generischen Auflistungen  
 Das folgende Beispiel veranschaulicht die Vorteile der Kontravarianz-Unterstützung in der <xref:System.Collections.Generic.IComparer%601>Schnittstelle.</xref:System.Collections.Generic.IComparer%601> Die `PersonComparer`-Klasse implementiert die `IComparer(Of Person)`-Schnittstelle. Jedoch können Sie diese Klasse, um eine Sequenz von Objekten eines vergleichen Wiederverwenden der `Employee` eingeben, da `Employee` erbt `Person`.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
