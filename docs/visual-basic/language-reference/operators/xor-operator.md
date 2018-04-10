---
title: Xor-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b14f11f2df2df9c29e88e9188390cfe245d2cb58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="c5a5a-102">Xor-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5a5a-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="c5a5a-103">Führt einen logischen Ausschluss für zwei `Boolean` Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5a5a-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c5a5a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="c5a5a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c5a5a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-106">Required.</span></span> <span data-ttu-id="c5a5a-107">Alle `Boolean` oder numerische Variable.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="c5a5a-108">Für den booleschen Vergleich `result` ist die logische Exklusion (exklusive logische Disjunktion) zweier `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="c5a5a-109">Für bitweise Operationen `result` ist ein numerischer Wert, der die bitweisen Ausschluss (exklusive bitweise Disjunktion) von zwei numerischen Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c5a5a-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-110">Required.</span></span> <span data-ttu-id="c5a5a-111">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c5a5a-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-112">Required.</span></span> <span data-ttu-id="c5a5a-113">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5a5a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5a5a-114">Remarks</span></span>  
 <span data-ttu-id="c5a5a-115">Für den booleschen Vergleich `result` ist `True` nur, wenn genau einem der `expression1` und `expression2` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="c5a5a-116">D. h. wenn `expression1` und `expression2` auswerten entgegengesetzte `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="c5a5a-117">Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c5a5a-118">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-118">If `expression1` is</span></span>|<span data-ttu-id="c5a5a-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-119">And `expression2` is</span></span>|<span data-ttu-id="c5a5a-120">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="c5a5a-121">In einen booleschen Vergleich zwischen den `Xor` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="c5a5a-122">Es gibt keine verkürzte Entsprechung zu `Xor`, da das Ergebnis immer beide Operanden abhängig.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="c5a5a-123">Für *verkürzte* logische Operatoren finden Sie unter [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c5a5a-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="c5a5a-124">Für bitweise Operationen der `Xor` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c5a5a-125">Wenn bit `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-125">If bit in `expression1` is</span></span>|<span data-ttu-id="c5a5a-126">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-126">And bit in `expression2` is</span></span>|<span data-ttu-id="c5a5a-127">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="c5a5a-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="c5a5a-128">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-128">1</span></span>|<span data-ttu-id="c5a5a-129">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-129">1</span></span>|<span data-ttu-id="c5a5a-130">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-130">0</span></span>|  
|<span data-ttu-id="c5a5a-131">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-131">1</span></span>|<span data-ttu-id="c5a5a-132">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-132">0</span></span>|<span data-ttu-id="c5a5a-133">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-133">1</span></span>|  
|<span data-ttu-id="c5a5a-134">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-134">0</span></span>|<span data-ttu-id="c5a5a-135">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-135">1</span></span>|<span data-ttu-id="c5a5a-136">1</span><span class="sxs-lookup"><span data-stu-id="c5a5a-136">1</span></span>|  
|<span data-ttu-id="c5a5a-137">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-137">0</span></span>|<span data-ttu-id="c5a5a-138">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-138">0</span></span>|<span data-ttu-id="c5a5a-139">0</span><span class="sxs-lookup"><span data-stu-id="c5a5a-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c5a5a-140">Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="c5a5a-141">Z. B. 5 `Xor` 3 ist 6.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="c5a5a-142">Um festzustellen, warum dies ist deshalb 5 und 3 in ihre binären Darstellungen, 101 und 011 konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="c5a5a-143">Ermitteln, dass 101 Xor 011 110, ist die binäre Darstellung der Dezimalzahl 6 mithilfe der vorherigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c5a5a-144">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c5a5a-144">Data Types</span></span>  
 <span data-ttu-id="c5a5a-145">Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="c5a5a-146">Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c5a5a-147">Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c5a5a-148">Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="c5a5a-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c5a5a-149">Überladen</span><span class="sxs-lookup"><span data-stu-id="c5a5a-149">Overloading</span></span>  
 <span data-ttu-id="c5a5a-150">Die `Xor` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c5a5a-151">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="c5a5a-152">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c5a5a-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5a5a-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5a5a-153">Example</span></span>  
 <span data-ttu-id="c5a5a-154">Im folgenden Beispiel wird die `Xor` Operator zwei Ausdrücke logischen Ausschluss (exklusive logische Disjunktion) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="c5a5a-155">Das Ergebnis ist ein `Boolean` -Wert, der angibt, ob genau einer der Ausdrücke ist `True`.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="c5a5a-156">Im vorherige Beispiel erzeugt die Ergebnisse der `False`, `True`, und `False`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5a5a-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5a5a-157">Example</span></span>  
 <span data-ttu-id="c5a5a-158">Im folgenden Beispiel wird die `Xor` Operator logischen Ausschluss (exklusive logische Disjunktion) der einzelnen Bits von zwei numerischen Ausdrücken ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="c5a5a-159">Das Bit im Ergebnismuster wird festgelegt, wenn nur eines der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="c5a5a-160">Im vorherige Beispiel werden die Ergebnisse von 2, 12 und 14, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c5a5a-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a5a-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5a5a-161">See Also</span></span>  
 [<span data-ttu-id="c5a5a-162">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5a5a-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="c5a5a-163">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5a5a-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="c5a5a-164">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c5a5a-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="c5a5a-165">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5a5a-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
