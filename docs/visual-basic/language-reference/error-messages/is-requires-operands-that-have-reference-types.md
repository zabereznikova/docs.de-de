---
title: "\"Is\" erfordert Operanden, die Verweistypen haben. Dieser Operand hat jedoch den Werttyp \"<typename>\"."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 5c9f156272cd0c3cbaeadbc0e162129f41619cc6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163349"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="e86cb-102">BC30020: "is" erfordert Operanden, die Verweis Typen haben. dieser Operand hat jedoch den Werttyp " \<typename> ".</span><span class="sxs-lookup"><span data-stu-id="e86cb-102">BC30020: 'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="e86cb-103">Der `Is` Vergleichs Operator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="e86cb-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="e86cb-104">Dieser Vergleich ist für Werttypen nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="e86cb-104">This comparison is not defined for value types.</span></span>

 <span data-ttu-id="e86cb-105">**Fehler-ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="e86cb-105">**Error ID:** BC30020</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e86cb-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e86cb-106">To correct this error</span></span>

- <span data-ttu-id="e86cb-107">Verwenden Sie den entsprechenden arithmetischen Vergleichs Operator oder den- `Like` Operator, um zwei Werttypen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="e86cb-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>

## <a name="see-also"></a><span data-ttu-id="e86cb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e86cb-108">See also</span></span>

- [<span data-ttu-id="e86cb-109">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="e86cb-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="e86cb-110">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="e86cb-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="e86cb-111">Comparison Operators (Vergleichsoperatoren)</span><span class="sxs-lookup"><span data-stu-id="e86cb-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
