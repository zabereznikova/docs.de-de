---
title: '&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; kann nur mit der verglichen werden &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505717"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="14ac2-102">&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; kann nur mit der verglichen werden &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="14ac2-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="14ac2-103">Eine Variable, die als auf NULL festlegbar deklariert wurde nicht auf einen Ausdruck verglichen wurde `Nothing` mithilfe der `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="14ac2-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="14ac2-104">**Fehler-ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="14ac2-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14ac2-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="14ac2-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="14ac2-106">Um einen Typ, der NULL zulässt, mithilfe des `Nothing` -Operators mit einem anderen Ausdruck als `IsNot` zu vergleichen, rufen Sie die `GetType` -Methode für den Typ, der NULL zulässt, auf und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="14ac2-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ac2-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14ac2-107">See also</span></span>
- [<span data-ttu-id="14ac2-108">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="14ac2-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="14ac2-109">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="14ac2-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
