---
title: Verwenden von Varianz in Delegaten (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 620fd61000e42d68f566e441d023d73a036000ae
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="e5139-102">Verwenden von Varianz in Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5139-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="e5139-103">Wenn Sie einen Delegaten eine Methode zuweisen *Kovarianz* und *Kontravarianz* bieten Flexibilität für den Abgleich eines Delegattyps mit einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="e5139-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="e5139-104">Kovarianz unterstützt eine Methode Rückgabetyp aufweisen, stärker abgeleiteten, als im Delegaten definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5139-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="e5139-105">Kontravarianz unterstützt eine Methode mit Parametertypen, die weniger stark abgeleitet sind als die in der Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="e5139-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="e5139-106">Beispiel 1: Kovarianz</span><span class="sxs-lookup"><span data-stu-id="e5139-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="e5139-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5139-107">Description</span></span>  
 <span data-ttu-id="e5139-108">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, deren Rückgabetypen von dem Rückgabetyp in der Signatur des Delegaten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e5139-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="e5139-109">Der zurückgegebene Datentyp `DogsHandler` ist vom Typ `Dogs`, die abgeleitet wird von der `Mammals` Typ, der in der Delegat definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5139-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5139-110">Code</span><span class="sxs-lookup"><span data-stu-id="e5139-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="e5139-111">Beispiel 2: Kontravarianz</span><span class="sxs-lookup"><span data-stu-id="e5139-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="e5139-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5139-112">Description</span></span>  
 <span data-ttu-id="e5139-113">In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, deren Parameter Basistypen des Delegattyps Signatur-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5139-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="e5139-114">Mithilfe von Kontravarianz können Sie einen Ereignishandler statt separate Handler.</span><span class="sxs-lookup"><span data-stu-id="e5139-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="e5139-115">Sie können z. B. einen Ereignishandler, der akzeptiert erstellen ein `EventArgs` Eingabeparameter, und verwenden Sie es mit eine `Button.MouseClick` -Ereignis, das gesendet ein `MouseEventArgs` Typ als Parameter und mit ein `TextBox.KeyDown` -Ereignis, das gesendet ein `KeyEventArgs` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5139-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e5139-116">Code</span><span class="sxs-lookup"><span data-stu-id="e5139-116">Code</span></span>  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
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
  
## <a name="see-also"></a><span data-ttu-id="e5139-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5139-117">See Also</span></span>  
 <span data-ttu-id="e5139-118">[Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="e5139-118">[Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
<span data-ttu-id="e5139-119"> [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="e5139-119"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
