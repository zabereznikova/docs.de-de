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
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="48780-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48780-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="48780-103">Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="48780-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48780-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48780-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="48780-105">Teile</span><span class="sxs-lookup"><span data-stu-id="48780-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="48780-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48780-106">Required.</span></span> <span data-ttu-id="48780-107">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="48780-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="48780-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48780-108">Required.</span></span> <span data-ttu-id="48780-109">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="48780-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48780-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48780-110">Remarks</span></span>  
 <span data-ttu-id="48780-111">Für `Boolean` Ausdrücke, die in der folgenden Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="48780-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="48780-112">Wenn `expression` ist</span><span class="sxs-lookup"><span data-stu-id="48780-112">If `expression` is</span></span>|<span data-ttu-id="48780-113">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="48780-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="48780-114">Bei numerischen Ausdrücken die `Not` Operator Invertiert die Bitwerte ein beliebiger numerischer Ausdruck, und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="48780-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="48780-115">Wenn bit `expression` ist</span><span class="sxs-lookup"><span data-stu-id="48780-115">If bit in `expression` is</span></span>|<span data-ttu-id="48780-116">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="48780-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="48780-117">1</span><span class="sxs-lookup"><span data-stu-id="48780-117">1</span></span>|<span data-ttu-id="48780-118">0</span><span class="sxs-lookup"><span data-stu-id="48780-118">0</span></span>|  
|<span data-ttu-id="48780-119">0</span><span class="sxs-lookup"><span data-stu-id="48780-119">0</span></span>|<span data-ttu-id="48780-120">1</span><span class="sxs-lookup"><span data-stu-id="48780-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="48780-121">Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="48780-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="48780-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="48780-122">Data Types</span></span>  
 <span data-ttu-id="48780-123">Bei einer booleschen Negation der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="48780-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="48780-124">Datentyp des Ergebnisses für eine bitweise Negation ist identisch mit der `expression`.</span><span class="sxs-lookup"><span data-stu-id="48780-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="48780-125">Allerdings ist der Ausdruck `Decimal`, das Ergebnis ist `Long`.</span><span class="sxs-lookup"><span data-stu-id="48780-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="48780-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="48780-126">Overloading</span></span>  
 <span data-ttu-id="48780-127">Die `Not` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="48780-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="48780-128">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="48780-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="48780-129">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="48780-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48780-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48780-130">Example</span></span>  
 <span data-ttu-id="48780-131">Im folgenden Beispiel wird die `Not` Operator auszuführenden logischen Negation für einen `Boolean` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="48780-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="48780-132">Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="48780-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="48780-133">Das obige Beispiel erzeugt die Ergebnisse der `False` und `True`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="48780-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48780-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48780-134">Example</span></span>  
 <span data-ttu-id="48780-135">Im folgenden Beispiel wird die `Not` Operator, um die logische Negation von den einzelnen Bit eines numerischen Ausdrucks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48780-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="48780-136">Das Bit im Ergebnismuster ist das Gegenteil des entsprechenden Bits in den Operandenmuster, einschließlich des Vorzeichenbits fest.</span><span class="sxs-lookup"><span data-stu-id="48780-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="48780-137">Im vorherige Beispiel werden die Ergebnisse von – 11 – 9 und –7, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="48780-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48780-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48780-138">See Also</span></span>  
 [<span data-ttu-id="48780-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48780-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="48780-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48780-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="48780-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="48780-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="48780-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48780-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
