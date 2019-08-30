---
title: Verwenden von Varianz in Delegaten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: ebba7e862e1b4677d9438aa301ef2b713fba3712
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169068"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="90509-102">Verwenden von Varianz in Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90509-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="90509-103">Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="90509-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="90509-104">Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ.</span><span class="sxs-lookup"><span data-stu-id="90509-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="90509-105">Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="90509-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="90509-106">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="90509-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="90509-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90509-107">Description</span></span>

<span data-ttu-id="90509-108">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="90509-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="90509-109">Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.</span><span class="sxs-lookup"><span data-stu-id="90509-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="90509-110">Code</span><span class="sxs-lookup"><span data-stu-id="90509-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="90509-111">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="90509-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="90509-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90509-112">Description</span></span>

<span data-ttu-id="90509-113">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter verfügen, deren Typen Basis Typen vom Delegatsignatur-Parametertyp sind.</span><span class="sxs-lookup"><span data-stu-id="90509-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="90509-114">Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden.</span><span class="sxs-lookup"><span data-stu-id="90509-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="90509-115">Im folgenden Beispiel werden zwei Delegaten verwendet:</span><span class="sxs-lookup"><span data-stu-id="90509-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="90509-116">Ein <xref:System.Windows.Forms.KeyEventHandler> Delegat, der die Signatur des [Button. KeyDown](xref:System.Windows.Forms.Control.KeyDown) -Ereignisses definiert.</span><span class="sxs-lookup"><span data-stu-id="90509-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="90509-117">Die Signatur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="90509-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="90509-118">Ein <xref:System.Windows.Forms.MouseEventHandler> Delegat, der die Signatur des [Button. moukliclick](xref:System.Windows.Forms.Control.MouseDown) -Ereignisses definiert.</span><span class="sxs-lookup"><span data-stu-id="90509-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="90509-119">Die Signatur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="90509-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="90509-120">Das Beispiel definiert einen Ereignishandler mit einem <xref:System.EventArgs> -Parameter und verwendet ihn, um das `Button.KeyDown` - `Button.MouseClick` Ereignis und das-Ereignis zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="90509-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="90509-121">Dies ist möglich, weil <xref:System.EventArgs> der Basistyp sowohl <xref:System.Windows.Forms.KeyEventArgs> von als auch <xref:System.Windows.Forms.MouseEventArgs>von ist.</span><span class="sxs-lookup"><span data-stu-id="90509-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="90509-122">Code</span><span class="sxs-lookup"><span data-stu-id="90509-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="90509-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90509-123">See also</span></span>

- [<span data-ttu-id="90509-124">Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="90509-124">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="90509-125">Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="90509-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
