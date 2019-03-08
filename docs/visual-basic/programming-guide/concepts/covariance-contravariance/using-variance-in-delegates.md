---
title: Verwenden von Varianz in Delegaten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 19eb3070c1b8359a4eb050e7cf2f16622f66ebe9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679793"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="3c5ab-102">Verwenden von Varianz in Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c5ab-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="3c5ab-103">Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="3c5ab-104">Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="3c5ab-105">Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="3c5ab-106">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="3c5ab-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="3c5ab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c5ab-107">Description</span></span>

<span data-ttu-id="3c5ab-108">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="3c5ab-109">Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="3c5ab-110">Code</span><span class="sxs-lookup"><span data-stu-id="3c5ab-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="3c5ab-111">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="3c5ab-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="3c5ab-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c5ab-112">Description</span></span>

<span data-ttu-id="3c5ab-113">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter eines Typs verfügen, die Basistypen von den Parametertypen in der Delegatsignatur sind.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="3c5ab-114">Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="3c5ab-115">Sie können zum Beispiel einen Ereignishandler erstellen, der einen `EventArgs`-Eingabeparameter annimmt und mit einem `Button.MouseClick`-Ereignis verwendet, das einen Typ `MouseEventArgs` als Parameter sendet. Außerdem können Sie ihn mit einem `TextBox.KeyDown`-Ereignis verwenden, das einen `KeyEventArgs`-Parameter sendet.</span><span class="sxs-lookup"><span data-stu-id="3c5ab-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>

### <a name="code"></a><span data-ttu-id="3c5ab-116">Code</span><span class="sxs-lookup"><span data-stu-id="3c5ab-116">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="3c5ab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c5ab-117">See also</span></span>

- [<span data-ttu-id="3c5ab-118">Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="3c5ab-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="3c5ab-119">Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="3c5ab-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
