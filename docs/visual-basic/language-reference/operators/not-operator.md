---
title: Not-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="b184c-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b184c-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="b184c-103">Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="b184c-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b184c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b184c-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b184c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b184c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b184c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b184c-106">Required.</span></span> <span data-ttu-id="b184c-107">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b184c-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="b184c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b184c-108">Required.</span></span> <span data-ttu-id="b184c-109">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b184c-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b184c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b184c-110">Remarks</span></span>  
 <span data-ttu-id="b184c-111">Für `Boolean` Ausdrücke, die in der folgenden Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="b184c-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b184c-112">Wenn `expression` ist</span><span class="sxs-lookup"><span data-stu-id="b184c-112">If `expression` is</span></span>|<span data-ttu-id="b184c-113">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="b184c-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="b184c-114">Bei numerischen Ausdrücken die `Not` Operator Invertiert die Bitwerte ein beliebiger numerischer Ausdruck, und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b184c-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="b184c-115">Wenn bit `expression` ist</span><span class="sxs-lookup"><span data-stu-id="b184c-115">If bit in `expression` is</span></span>|<span data-ttu-id="b184c-116">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="b184c-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="b184c-117">1</span><span class="sxs-lookup"><span data-stu-id="b184c-117">1</span></span>|<span data-ttu-id="b184c-118">0</span><span class="sxs-lookup"><span data-stu-id="b184c-118">0</span></span>|  
|<span data-ttu-id="b184c-119">0</span><span class="sxs-lookup"><span data-stu-id="b184c-119">0</span></span>|<span data-ttu-id="b184c-120">1</span><span class="sxs-lookup"><span data-stu-id="b184c-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b184c-121">Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b184c-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b184c-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b184c-122">Data Types</span></span>  
 <span data-ttu-id="b184c-123">Bei einer booleschen Negation der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b184c-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="b184c-124">Datentyp des Ergebnisses für eine bitweise Negation ist identisch mit der `expression`.</span><span class="sxs-lookup"><span data-stu-id="b184c-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="b184c-125">Allerdings ist der Ausdruck `Decimal`, das Ergebnis ist `Long`.</span><span class="sxs-lookup"><span data-stu-id="b184c-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b184c-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="b184c-126">Overloading</span></span>  
 <span data-ttu-id="b184c-127">Die `Not` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="b184c-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b184c-128">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="b184c-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b184c-129">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b184c-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b184c-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b184c-130">Example</span></span>  
 <span data-ttu-id="b184c-131">Im folgenden Beispiel wird die `Not` Operator auszuführenden logischen Negation für einen `Boolean` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b184c-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="b184c-132">Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="b184c-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="b184c-133">Das obige Beispiel erzeugt die Ergebnisse der `False` und `True`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b184c-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b184c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b184c-134">Example</span></span>  
 <span data-ttu-id="b184c-135">Im folgenden Beispiel wird die `Not` Operator, um die logische Negation von den einzelnen Bit eines numerischen Ausdrucks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b184c-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="b184c-136">Das Bit im Ergebnismuster ist das Gegenteil des entsprechenden Bits in den Operandenmuster, einschließlich des Vorzeichenbits fest.</span><span class="sxs-lookup"><span data-stu-id="b184c-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="b184c-137">Im vorherige Beispiel werden die Ergebnisse von – 11 – 9 und –7, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b184c-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b184c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b184c-138">See Also</span></span>  
 [<span data-ttu-id="b184c-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b184c-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="b184c-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b184c-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b184c-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b184c-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b184c-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b184c-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
