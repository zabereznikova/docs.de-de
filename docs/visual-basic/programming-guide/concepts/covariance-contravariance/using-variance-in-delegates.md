---
title: Verwenden von Varianz bei Delegaten
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 9c2aad0e4b9408939600938412fe5c3e73b5bf15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349030"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="11258-102">Using Variance in Delegates (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11258-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="11258-103">Wenn Sie einem Delegat eine Methode zuweisen, bieten *Kovarianz* und *Kontravarianz* Flexibilität für das Abgleichen eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="11258-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="11258-104">Kovarianz lässt die Verfügung einer Methode über einen Rückgabetyp zu, der stärker abgeleitet ist als der im Delegat definierte Typ.</span><span class="sxs-lookup"><span data-stu-id="11258-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="11258-105">Kontravarianz lässt eine Methode zu, die über Typen verfügt, die weniger abgeleitet sind als die im Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="11258-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="11258-106">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="11258-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="11258-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11258-107">Description</span></span>

<span data-ttu-id="11258-108">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Rückgabetypen verfügen, die von den Rückgabetypen in der Delegatsignatur abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="11258-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="11258-109">Der von `DogsHandler` zurückgegebene Datentyp ist vom Typ `Dogs`, der vom im Delegat definierten Typ `Mammals` abhängt.</span><span class="sxs-lookup"><span data-stu-id="11258-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="11258-110">Code</span><span class="sxs-lookup"><span data-stu-id="11258-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="11258-111">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="11258-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="11258-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11258-112">Description</span></span>

<span data-ttu-id="11258-113">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, die über Parameter eines Typs verfügen, die Basistypen von den Parametertypen der Delegatsignatur sind.</span><span class="sxs-lookup"><span data-stu-id="11258-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="11258-114">Mithilfe von Kontravarianz können Sie einen Ereignishandler anstelle getrennter Handler verwenden.</span><span class="sxs-lookup"><span data-stu-id="11258-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="11258-115">Im folgenden Beispiel werden zwei Delegaten verwendet:</span><span class="sxs-lookup"><span data-stu-id="11258-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="11258-116">Ein <xref:System.Windows.Forms.KeyEventHandler>-Delegat, der die Signatur des Ereignisses [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) definiert.</span><span class="sxs-lookup"><span data-stu-id="11258-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="11258-117">Die Signatur lautet:</span><span class="sxs-lookup"><span data-stu-id="11258-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="11258-118">Ein <xref:System.Windows.Forms.MouseEventHandler>-Delegat, der die Signatur des Ereignisses [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) definiert.</span><span class="sxs-lookup"><span data-stu-id="11258-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="11258-119">Die Signatur lautet:</span><span class="sxs-lookup"><span data-stu-id="11258-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="11258-120">Das Beispiel definiert einen Ereignishandler mit einem <xref:System.EventArgs>-Parameter und verwendet diesen, um die Ereignisse `Button.KeyDown` und `Button.MouseClick` zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="11258-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="11258-121">Dies ist möglich, weil <xref:System.EventArgs> der Basistyp sowohl von <xref:System.Windows.Forms.KeyEventArgs> als auch von <xref:System.Windows.Forms.MouseEventArgs> ist.</span><span class="sxs-lookup"><span data-stu-id="11258-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="11258-122">Code</span><span class="sxs-lookup"><span data-stu-id="11258-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="11258-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11258-123">See also</span></span>

- [<span data-ttu-id="11258-124">Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="11258-124">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="11258-125">Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="11258-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
