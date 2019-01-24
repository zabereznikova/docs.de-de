---
title: Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: a6ddbaa358709fe306f1529112d1f2bd0a715a91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646944"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="08b7f-102">Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird</span><span class="sxs-lookup"><span data-stu-id="08b7f-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="08b7f-103">Der Compiler nimmt keine Konvertierung eines anonymen in eine Ausdrucksbaumstruktur, wenn eine Eigenschaft des anonymen Typs verwendet wird, um eine andere Eigenschaft des anonymen Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="08b7f-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="08b7f-104">In den folgenden Code, z. B. `Prop1` in der Initialisierungsliste deklariert wird, und klicken Sie dann als der Anfangswert für verwendet `Prop2`.</span><span class="sxs-lookup"><span data-stu-id="08b7f-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
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
  
 <span data-ttu-id="08b7f-105">**Fehler-ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="08b7f-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08b7f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="08b7f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="08b7f-107">Weisen Sie den Anfangswert für `Prop1` an eine lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="08b7f-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="08b7f-108">Weisen Sie diese Variable sowohl `Prop1` und `Prop2`, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="08b7f-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="08b7f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08b7f-109">See also</span></span>

- [<span data-ttu-id="08b7f-110">Anonyme Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08b7f-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="08b7f-111">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08b7f-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="08b7f-112">Vorgehensweise: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08b7f-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
