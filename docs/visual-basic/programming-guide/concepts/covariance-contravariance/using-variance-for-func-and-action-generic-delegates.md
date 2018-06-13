---
title: Verwenden von Varianz für Func und Action generische Delegaten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
ms.openlocfilehash: e4c878f65867c575a1691423df583662d72a257c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642934"
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="dfbe5-102">Verwenden von Varianz für Func und Action generische Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfbe5-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>
<span data-ttu-id="dfbe5-103">Diese Beispiele veranschaulichen, wie Sie Kovarianz und Kontravarianz in den generischen Delegaten `Func` und `Action` verwenden, um die Wiederverwendung von Methoden zu ermöglichen und mehr Flexibilität in Ihrem Code zu bieten.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="dfbe5-104">Weitere Informationen zu ko- und Kontravarianz finden Sie unter [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="dfbe5-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="dfbe5-105">Verwendung von Delegaten mit kovarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="dfbe5-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="dfbe5-106">Das folgende Beispiel veranschaulicht die Vorteile der Unterstützung von Kovarianz in generischen `Func`-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="dfbe5-107">Die Methode `FindByTitle` nimmt einen Parameter vom Typ `String` entgegen und gibt ein Objekt vom Typ `Employee` zurück.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="dfbe5-108">Allerdings können Sie diese Methode dem Delegaten `Func(Of String, Person)` zuweisen, da `Employee` `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="dfbe5-109">Verwendung von Delegaten mit kontravarianten Typparametern</span><span class="sxs-lookup"><span data-stu-id="dfbe5-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="dfbe5-110">Im folgenden Beispiel werden die Vorteile der Unterstützung von Kontravarianz in generischen `Action`-Delegaten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="dfbe5-111">Die `AddToContacts`-Methode nimmt einen Parameter vom Typ `Person` entgegen.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="dfbe5-112">Allerdings können Sie diese Methode dem Delegaten `Action(Of Employee)` zuweisen, da `Employee` `Person` erbt.</span><span class="sxs-lookup"><span data-stu-id="dfbe5-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dfbe5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfbe5-113">See Also</span></span>  
 [<span data-ttu-id="dfbe5-114">Kovarianz und Kontravarianz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfbe5-114">Covariance and Contravariance (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="dfbe5-115">Generika</span><span class="sxs-lookup"><span data-stu-id="dfbe5-115">Generics</span></span>](~/docs/standard/generics/index.md)
