---
title: "\"Is\" erfordert Operanden, die Verweistypen haben. Dieser Operand hat jedoch den Werttyp \"<typename>\"."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: e5acc94a3738fca3a43740bdba727fc843132aa1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402810"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="9dd68-102">"Is" erfordert Operanden, die Verweistypen haben. Dieser Operand hat jedoch den Werttyp "\<typename>".</span><span class="sxs-lookup"><span data-stu-id="9dd68-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="9dd68-103">Der `Is` Vergleichs Operator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="9dd68-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="9dd68-104">Dieser Vergleich ist für Werttypen nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="9dd68-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="9dd68-105">**Fehler-ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="9dd68-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9dd68-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9dd68-106">To correct this error</span></span>  
  
- <span data-ttu-id="9dd68-107">Verwenden Sie den entsprechenden arithmetischen Vergleichs Operator oder den- `Like` Operator, um zwei Werttypen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9dd68-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd68-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9dd68-108">See also</span></span>

- [<span data-ttu-id="9dd68-109">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="9dd68-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="9dd68-110">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="9dd68-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="9dd68-111">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="9dd68-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
