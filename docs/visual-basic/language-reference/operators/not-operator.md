---
title: Not-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 29e2b159e4c6261a62e788b537102b9b457fe0c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955823"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="c97c3-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c97c3-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="c97c3-103">Führt eine logische Negation für `Boolean` einen-Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks aus.</span><span class="sxs-lookup"><span data-stu-id="c97c3-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c97c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c97c3-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="c97c3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="c97c3-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c97c3-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c97c3-106">Required.</span></span> <span data-ttu-id="c97c3-107">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c97c3-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="c97c3-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c97c3-108">Required.</span></span> <span data-ttu-id="c97c3-109">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c97c3-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c97c3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c97c3-110">Remarks</span></span>  
 <span data-ttu-id="c97c3-111">In `Boolean` der folgenden Tabelle wird für Ausdrücke veranschaulicht `result` , wie bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c97c3-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c97c3-112">Wenn `expression` ist</span><span class="sxs-lookup"><span data-stu-id="c97c3-112">If `expression` is</span></span>|<span data-ttu-id="c97c3-113">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="c97c3-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="c97c3-114">Bei numerischen Ausdrücken kehrt der `Not` Operator die Bitwerte eines beliebigen numerischen Ausdrucks um und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="c97c3-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c97c3-115">Wenn Bit in `expression`</span><span class="sxs-lookup"><span data-stu-id="c97c3-115">If bit in `expression` is</span></span>|<span data-ttu-id="c97c3-116">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="c97c3-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="c97c3-117">1</span><span class="sxs-lookup"><span data-stu-id="c97c3-117">1</span></span>|<span data-ttu-id="c97c3-118">0</span><span class="sxs-lookup"><span data-stu-id="c97c3-118">0</span></span>|  
|<span data-ttu-id="c97c3-119">0</span><span class="sxs-lookup"><span data-stu-id="c97c3-119">0</span></span>|<span data-ttu-id="c97c3-120">1</span><span class="sxs-lookup"><span data-stu-id="c97c3-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c97c3-121">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="c97c3-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c97c3-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c97c3-122">Data Types</span></span>  
 <span data-ttu-id="c97c3-123">Bei einer booleschen Negation ist `Boolean`der Datentyp des Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="c97c3-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c97c3-124">Bei einer bitweisen Negation ist der Ergebnis Datentyp mit dem von `expression`identisch.</span><span class="sxs-lookup"><span data-stu-id="c97c3-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="c97c3-125">Wenn Expression jedoch ist `Decimal`, ist `Long`das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="c97c3-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c97c3-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="c97c3-126">Overloading</span></span>  
 <span data-ttu-id="c97c3-127">Der `Not` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="c97c3-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="c97c3-128">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="c97c3-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c97c3-129">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c97c3-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c97c3-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c97c3-130">Example</span></span>  
 <span data-ttu-id="c97c3-131">Im folgenden Beispiel wird der `Not` -Operator verwendet, um eine logische `Boolean` Negation für einen-Ausdruck auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c97c3-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="c97c3-132">Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="c97c3-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="c97c3-133">Das vorherige Beispiel erzeugt die Ergebnisse `False` von `True`und.</span><span class="sxs-lookup"><span data-stu-id="c97c3-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c97c3-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c97c3-134">Example</span></span>  
 <span data-ttu-id="c97c3-135">Im folgenden Beispiel wird der `Not` -Operator verwendet, um eine logische Negation der einzelnen Bits eines numerischen Ausdrucks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c97c3-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="c97c3-136">Das Bit im Ergebnis Muster wird auf das Gegenteil des entsprechenden Bits im Operanden Muster festgelegt, einschließlich des Signier Bits.</span><span class="sxs-lookup"><span data-stu-id="c97c3-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="c97c3-137">Im vorherigen Beispiel werden die Ergebnisse von – 11, – 9 bzw. – 7 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c97c3-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97c3-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c97c3-138">See also</span></span>

- [<span data-ttu-id="c97c3-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c97c3-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c97c3-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c97c3-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c97c3-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c97c3-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c97c3-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c97c3-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
