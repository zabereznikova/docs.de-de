---
title: Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: d43f6ef19591af326d06a4ce21194d8f9fa58c2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585475"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="1e0a9-102">Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird</span><span class="sxs-lookup"><span data-stu-id="1e0a9-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="1e0a9-103">Der Compiler akzeptiert keine Konvertierung eines anonymen in einer Ausdrucksbaumstruktur dar, wenn eine Eigenschaft des anonymen Typs verwendet wird, um eine andere Eigenschaft des anonymen Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1e0a9-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="1e0a9-104">Im folgenden Code wird z. B. `Prop1` in der Initialisierungsliste deklariert wird, und klicken Sie dann als der ursprüngliche Wert verwendet `Prop2`.</span><span class="sxs-lookup"><span data-stu-id="1e0a9-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1e0a9-105">**Fehler-ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="1e0a9-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1e0a9-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1e0a9-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1e0a9-107">Weisen Sie den Anfangswert für `Prop1` an eine lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="1e0a9-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="1e0a9-108">Weisen Sie diese Variable sowohl `Prop1` und `Prop2`, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e0a9-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1e0a9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e0a9-109">See Also</span></span>  
 [<span data-ttu-id="1e0a9-110">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="1e0a9-110">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="1e0a9-111">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="1e0a9-111">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [<span data-ttu-id="1e0a9-112">Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen</span><span class="sxs-lookup"><span data-stu-id="1e0a9-112">How to: Use Expression Trees to Build Dynamic Queries</span></span>](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
