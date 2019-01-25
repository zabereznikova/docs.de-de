---
title: '&#39;Ist&#39; erfordert Operanden, die Verweistypen haben, aber dieser Operand hat den Werttyp &#39; &lt;Typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 0b3f80e98087e455ec730dea8c57478528e9259c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722919"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="51fa8-102">&#39;Ist&#39; erfordert Operanden, die Verweistypen haben, aber dieser Operand hat den Werttyp &#39; &lt;Typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="51fa8-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="51fa8-103">Die `Is` Vergleichsoperator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="51fa8-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="51fa8-104">Dieser Vergleich ist für Werttypen nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="51fa8-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="51fa8-105">**Fehler-ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="51fa8-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51fa8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="51fa8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="51fa8-107">Verwenden Sie den entsprechenden arithmetischen Vergleichsoperator oder `Like` Operator, um zwei Werttypen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="51fa8-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fa8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51fa8-108">See also</span></span>
- [<span data-ttu-id="51fa8-109">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="51fa8-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="51fa8-110">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="51fa8-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="51fa8-111">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="51fa8-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
