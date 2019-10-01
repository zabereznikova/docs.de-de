---
title: Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701177"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="ccdec-102">Eine Konvertierung des anonymen Typs in eine Ausdrucksbaumstruktur ist nicht möglich, da sie ein Feld enthält, das in der Initialisierung eines anderen Feldes verwendet wird</span><span class="sxs-lookup"><span data-stu-id="ccdec-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="ccdec-103">Der Compiler akzeptiert die Konvertierung einer anonymen in eine Ausdrucks Baumstruktur nicht, wenn eine Eigenschaft des anonymen Typs verwendet wird, um eine andere Eigenschaft des anonymen Typs zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ccdec-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="ccdec-104">Im folgenden Code wird z. b. `Prop1` in der Initialisierungs Liste deklariert und dann als Anfangswert für `Prop2` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ccdec-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
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
  
 <span data-ttu-id="ccdec-105">**Fehler-ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="ccdec-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ccdec-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ccdec-106">To correct this error</span></span>  
  
- <span data-ttu-id="ccdec-107">Weisen Sie den Anfangswert für `Prop1` einer lokalen Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="ccdec-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="ccdec-108">Weisen Sie die Variable `Prop1` und `Prop2` zu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccdec-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ccdec-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccdec-109">See also</span></span>

- [<span data-ttu-id="ccdec-110">Anonyme Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccdec-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="ccdec-111">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccdec-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="ccdec-112">Vorgehensweise: Verwenden von Ausdrucks Baumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic) </span><span class="sxs-lookup"><span data-stu-id="ccdec-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
