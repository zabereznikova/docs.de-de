---
title: Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 2f97a0de74428ce42a088644580a78bf8fd99945
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936801"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="147d2-102">Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird</span><span class="sxs-lookup"><span data-stu-id="147d2-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="147d2-103">Der Compiler nimmt keine Konvertierung eines anonymen in eine Ausdrucksbaumstruktur, wenn eine Eigenschaft des anonymen Typs verwendet wird, um eine andere Eigenschaft des anonymen Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="147d2-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="147d2-104">In den folgenden Code, z. B. `Prop1` in der Initialisierungsliste deklariert wird, und klicken Sie dann als der Anfangswert für verwendet `Prop2`.</span><span class="sxs-lookup"><span data-stu-id="147d2-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
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
  
 <span data-ttu-id="147d2-105">**Fehler-ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="147d2-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="147d2-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="147d2-106">To correct this error</span></span>  
  
-   <span data-ttu-id="147d2-107">Weisen Sie den Anfangswert für `Prop1` an eine lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="147d2-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="147d2-108">Weisen Sie diese Variable sowohl `Prop1` und `Prop2`, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="147d2-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="147d2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="147d2-109">See also</span></span>

[<span data-ttu-id="147d2-110">Anonyme Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="147d2-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
[<span data-ttu-id="147d2-111">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="147d2-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)  
[<span data-ttu-id="147d2-112">Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="147d2-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)  