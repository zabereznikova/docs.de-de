---
title: '&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; nur verglichen werden können, um &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="545cd-102">&#39;IsNot&#39; -Operand vom Typ &#39;Typename&#39; nur verglichen werden können, um &#39;nichts&#39;, da &#39;Typename&#39; ist ein NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="545cd-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="545cd-103">Eine Variable, die als auf NULL festlegbar deklariert wurde wurde im Vergleich zu einem Ausdruck außer `Nothing` mithilfe der `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="545cd-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="545cd-104">**Fehler-ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="545cd-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="545cd-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="545cd-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="545cd-106">Außer den nullable-Typ in einen Ausdruck vergleichen `Nothing` mithilfe der `IsNot` -Operator, rufen die `GetType` Methode für die nullable-Typ und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="545cd-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="545cd-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="545cd-107">See Also</span></span>  
 [<span data-ttu-id="545cd-108">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="545cd-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="545cd-109">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="545cd-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
