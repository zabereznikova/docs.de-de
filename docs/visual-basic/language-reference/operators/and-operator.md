---
title: And-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="60a55-102">And-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60a55-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="60a55-103">Führt eine logische Konjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="60a55-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60a55-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="60a55-105">Teile</span><span class="sxs-lookup"><span data-stu-id="60a55-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="60a55-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60a55-106">Required.</span></span> <span data-ttu-id="60a55-107">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="60a55-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="60a55-108">Für den booleschen Vergleich `result` ist die logische Konjunktion zweier `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="60a55-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="60a55-109">Für bitweise Operationen `result` ist ein numerischer Wert, der die bitweise Konjunktion von zwei numerischen Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="60a55-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="60a55-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60a55-110">Required.</span></span> <span data-ttu-id="60a55-111">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="60a55-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="60a55-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="60a55-112">Required.</span></span> <span data-ttu-id="60a55-113">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="60a55-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60a55-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60a55-114">Remarks</span></span>  
 <span data-ttu-id="60a55-115">Für den booleschen Vergleich `result` ist `True` Wenn und nur wenn beide `expression1` und `expression2` ergeben `True`.</span><span class="sxs-lookup"><span data-stu-id="60a55-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="60a55-116">Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="60a55-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="60a55-117">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-117">If `expression1` is</span></span>|<span data-ttu-id="60a55-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-118">And `expression2` is</span></span>|<span data-ttu-id="60a55-119">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="60a55-120">In einen booleschen Vergleich zwischen den `And` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="60a55-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="60a55-121">Die [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *verkürzte*, was bedeutet, dass bei `expression1` ist `False`, klicken Sie dann `expression2` wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="60a55-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="60a55-122">Bei Anwendung auf numerische Werte, die `And` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="60a55-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="60a55-123">Wenn bit `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-123">If bit in `expression1` is</span></span>|<span data-ttu-id="60a55-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-124">And bit in `expression2` is</span></span>|<span data-ttu-id="60a55-125">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="60a55-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="60a55-126">1</span><span class="sxs-lookup"><span data-stu-id="60a55-126">1</span></span>|<span data-ttu-id="60a55-127">1</span><span class="sxs-lookup"><span data-stu-id="60a55-127">1</span></span>|<span data-ttu-id="60a55-128">1</span><span class="sxs-lookup"><span data-stu-id="60a55-128">1</span></span>|  
|<span data-ttu-id="60a55-129">1</span><span class="sxs-lookup"><span data-stu-id="60a55-129">1</span></span>|<span data-ttu-id="60a55-130">0</span><span class="sxs-lookup"><span data-stu-id="60a55-130">0</span></span>|<span data-ttu-id="60a55-131">0</span><span class="sxs-lookup"><span data-stu-id="60a55-131">0</span></span>|  
|<span data-ttu-id="60a55-132">0</span><span class="sxs-lookup"><span data-stu-id="60a55-132">0</span></span>|<span data-ttu-id="60a55-133">1</span><span class="sxs-lookup"><span data-stu-id="60a55-133">1</span></span>|<span data-ttu-id="60a55-134">0</span><span class="sxs-lookup"><span data-stu-id="60a55-134">0</span></span>|  
|<span data-ttu-id="60a55-135">0</span><span class="sxs-lookup"><span data-stu-id="60a55-135">0</span></span>|<span data-ttu-id="60a55-136">0</span><span class="sxs-lookup"><span data-stu-id="60a55-136">0</span></span>|<span data-ttu-id="60a55-137">0</span><span class="sxs-lookup"><span data-stu-id="60a55-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="60a55-138">Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um genaue Ergebnisse sicherzustellen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="60a55-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="60a55-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="60a55-139">Data Types</span></span>  
 <span data-ttu-id="60a55-140">Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.</span><span class="sxs-lookup"><span data-stu-id="60a55-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="60a55-141">Für einen booleschen Vergleich, der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="60a55-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="60a55-142">Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="60a55-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="60a55-143">Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="60a55-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60a55-144">Die `And` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="60a55-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="60a55-145">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="60a55-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="60a55-146">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="60a55-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60a55-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60a55-147">Example</span></span>  
 <span data-ttu-id="60a55-148">Im folgenden Beispiel wird die `And` Operator, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="60a55-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="60a55-149">Das Ergebnis ist ein `Boolean` -Wert, der angibt, ob die beiden Ausdrücke sind `True`.</span><span class="sxs-lookup"><span data-stu-id="60a55-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 <span data-ttu-id="60a55-150">Das obige Beispiel erzeugt die Ergebnisse der `True` und `False`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="60a55-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60a55-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60a55-151">Example</span></span>  
 <span data-ttu-id="60a55-152">Im folgenden Beispiel wird die `And` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken logische Konjunktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="60a55-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="60a55-153">Das Bit im Ergebnismuster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60a55-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 <span data-ttu-id="60a55-154">Im vorherige Beispiel werden die Ergebnisse von 8, 2 und 0 (null) bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="60a55-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a55-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60a55-155">See Also</span></span>  
 [<span data-ttu-id="60a55-156">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60a55-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="60a55-157">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60a55-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="60a55-158">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="60a55-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="60a55-159">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="60a55-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [<span data-ttu-id="60a55-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60a55-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
