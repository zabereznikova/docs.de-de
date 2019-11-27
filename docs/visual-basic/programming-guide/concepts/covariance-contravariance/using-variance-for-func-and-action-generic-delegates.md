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
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="bdcdb-102">Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdcdb-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>

<span data-ttu-id="bdcdb-103">Diese Beispiele veranschaulichen, wie Sie Kovarianz und Kontravarianz in den generischen Delegaten `Func` und `Action` verwenden, um die Wiederverwendung von Methoden zu ermöglichen und mehr Flexibilität in Ihrem Code zu bieten.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>

<span data-ttu-id="bdcdb-104">Weitere Informationen über Kovarianz und Kontra Varianz finden Sie unter [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="bdcdb-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>

## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="bdcdb-105">Verwendung von Delegaten mit kovarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="bdcdb-105">Using Delegates with Covariant Type Parameters</span></span>

<span data-ttu-id="bdcdb-106">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in generischen `Func`-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="bdcdb-107">Die Methode `FindByTitle` nimmt einen Parameter vom Typ `String` entgegen und gibt ein Objekt vom Typ `Employee` zurück.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="bdcdb-108">Allerdings können Sie diese Methode dem Delegaten `Func(Of String, Person)` zuweisen, da `Employee` `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>

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

## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="bdcdb-109">Verwendung von Delegaten mit kontravarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="bdcdb-109">Using Delegates with Contravariant Type Parameters</span></span>

<span data-ttu-id="bdcdb-110">Im folgenden Beispiel werden die Vorteile der Unterstützung von Kontravarianz in generischen `Action`-Delegaten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="bdcdb-111">Die `AddToContacts`-Methode nimmt einen Parameter vom Typ `Person` entgegen.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="bdcdb-112">Allerdings können Sie diese Methode dem Delegaten `Action(Of Employee)` zuweisen, da `Employee` `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="bdcdb-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bdcdb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdcdb-113">See also</span></span>

- [<span data-ttu-id="bdcdb-114">Kovarianz und Kontravarianz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdcdb-114">Covariance and Contravariance (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="bdcdb-115">Generics</span><span class="sxs-lookup"><span data-stu-id="bdcdb-115">Generics</span></span>](../../../../standard/generics/index.md)
