---
title: Verwenden von Varianz für die generischen Delegaten Func und Action
ms.date: 07/20/2015
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
ms.openlocfilehash: 2678abd03f55224720d00509dc44f2db16551193
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349045"
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>Using Variance for Func and Action Generic Delegates (Visual Basic)

Diese Beispiele veranschaulichen, wie Sie Kovarianz und Kontravarianz in den generischen Delegaten `Func` und `Action` verwenden, um die Wiederverwendung von Methoden zu ermöglichen und mehr Flexibilität in Ihrem Code zu bieten.

For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).

## <a name="using-delegates-with-covariant-type-parameters"></a>Verwendung von Delegaten mit kovarianten Typparametern

Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in generischen `Func`-Delegaten. Die Methode `FindByTitle` nimmt einen Parameter vom Typ `String` entgegen und gibt ein Objekt vom Typ `Employee` zurück. Allerdings können Sie diese Methode dem Delegaten `Func(Of String, Person)` zuweisen, da `Employee` `Person` erbt.

```vb
' Simple hierarchy of classes.
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class Finder
    Public Shared Function FindByTitle(
        ByVal title As String) As Employee
        ' This is a stub for a method that returns
        ' an employee that has the specified title.
        Return New Employee
    End Function

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim findEmployee As Func(Of String, Employee) =
            AddressOf FindByTitle

        ' The delegate expects a method to return Person,
        ' but you can assign it a method that returns Employee.
        Dim findPerson As Func(Of String, Person) =
            AddressOf FindByTitle

        ' You can also assign a delegate
        ' that returns a more derived type to a delegate
        ' that returns a less derived type.
        findPerson = findEmployee
    End Sub
End Class
```

## <a name="using-delegates-with-contravariant-type-parameters"></a>Verwendung von Delegaten mit kontravarianten Typparametern

Im folgenden Beispiel werden die Vorteile der Unterstützung von Kontravarianz in generischen `Action`-Delegaten veranschaulicht. Die `AddToContacts`-Methode nimmt einen Parameter vom Typ `Person` entgegen. Allerdings können Sie diese Methode dem Delegaten `Action(Of Employee)` zuweisen, da `Employee` `Person` erbt.

```vb
Public Class Person
End Class

Public Class Employee
    Inherits Person
End Class

Class AddressBook
    Shared Sub AddToContacts(ByVal person As Person)
        ' This method adds a Person object
        ' to a contact list.
    End Sub

    Sub Test()
        ' Create an instance of the delegate without using variance.
        Dim addPersonToContacts As Action(Of Person) =
            AddressOf AddToContacts

        ' The Action delegate expects
        ' a method that has an Employee parameter,
        ' but you can assign it a method that has a Person parameter
        ' because Employee derives from Person.
        Dim addEmployeeToContacts As Action(Of Employee) =
            AddressOf AddToContacts

        ' You can also assign a delegate
        ' that accepts a less derived parameter
        ' to a delegate that accepts a more derived parameter.
        addEmployeeToContacts = addPersonToContacts
    End Sub
End Class
```

## <a name="see-also"></a>Siehe auch

- [Kovarianz und Kontravarianz (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)
- [Generics](../../../../standard/generics/index.md)
