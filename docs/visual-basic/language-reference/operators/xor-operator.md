---
title: Xor-Operator (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: bc3df1fdee5405445b4534a6982383c49b369b01
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980437"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="1be85-102">Xor-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1be85-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="1be85-103">Führt einen logischen Ausschluss für zwei `Boolean` Ausdrücke oder eine bitweise Exklusion zweier numerischer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="1be85-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1be85-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="1be85-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1be85-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="1be85-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1be85-106">Required.</span></span> <span data-ttu-id="1be85-107">Alle `Boolean` oder numerischen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1be85-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="1be85-108">Boolescher Vergleich `result` ist der logische Ausschluss (exklusive logische Disjunktion) von zwei `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="1be85-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="1be85-109">Für bitweise Operationen: `result` ist ein numerischer Wert, der den bitweisen Ausschluss (exklusive bitweise Disjunktion) aus zwei numerischen Bitmustern darstellt.</span><span class="sxs-lookup"><span data-stu-id="1be85-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="1be85-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1be85-110">Required.</span></span> <span data-ttu-id="1be85-111">Alle `Boolean` oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1be85-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1be85-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1be85-112">Required.</span></span> <span data-ttu-id="1be85-113">Alle `Boolean` oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1be85-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1be85-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1be85-114">Remarks</span></span>  
 <span data-ttu-id="1be85-115">Boolescher Vergleich `result` ist `True` nur, wenn genau eines der `expression1` und `expression2` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="1be85-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="1be85-116">D. h. wenn `expression1` und `expression2` auswerten entgegengesetzte `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="1be85-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="1be85-117">In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="1be85-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="1be85-118">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-118">If `expression1` is</span></span>|<span data-ttu-id="1be85-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-119">And `expression2` is</span></span>|<span data-ttu-id="1be85-120">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="1be85-121">In einen booleschen Vergleich zwischen den `Xor` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1be85-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="1be85-122">Es gibt keine verkürzte Entsprechung zum `Xor`, da das Ergebnis immer beide Operanden abhängig.</span><span class="sxs-lookup"><span data-stu-id="1be85-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="1be85-123">Für *kurzschließen* logische Operatoren finden Sie unter [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1be85-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="1be85-124">Für bitweise Operationen: die `Xor` Operator führt einen bitweisen Vergleich gleich positionierter Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1be85-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="1be85-125">Wenn bit `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-125">If bit in `expression1` is</span></span>|<span data-ttu-id="1be85-126">Ist und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-126">And bit in `expression2` is</span></span>|<span data-ttu-id="1be85-127">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="1be85-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="1be85-128">1</span><span class="sxs-lookup"><span data-stu-id="1be85-128">1</span></span>|<span data-ttu-id="1be85-129">1</span><span class="sxs-lookup"><span data-stu-id="1be85-129">1</span></span>|<span data-ttu-id="1be85-130">0</span><span class="sxs-lookup"><span data-stu-id="1be85-130">0</span></span>|  
|<span data-ttu-id="1be85-131">1</span><span class="sxs-lookup"><span data-stu-id="1be85-131">1</span></span>|<span data-ttu-id="1be85-132">0</span><span class="sxs-lookup"><span data-stu-id="1be85-132">0</span></span>|<span data-ttu-id="1be85-133">1</span><span class="sxs-lookup"><span data-stu-id="1be85-133">1</span></span>|  
|<span data-ttu-id="1be85-134">0</span><span class="sxs-lookup"><span data-stu-id="1be85-134">0</span></span>|<span data-ttu-id="1be85-135">1</span><span class="sxs-lookup"><span data-stu-id="1be85-135">1</span></span>|<span data-ttu-id="1be85-136">1</span><span class="sxs-lookup"><span data-stu-id="1be85-136">1</span></span>|  
|<span data-ttu-id="1be85-137">0</span><span class="sxs-lookup"><span data-stu-id="1be85-137">0</span></span>|<span data-ttu-id="1be85-138">0</span><span class="sxs-lookup"><span data-stu-id="1be85-138">0</span></span>|<span data-ttu-id="1be85-139">0</span><span class="sxs-lookup"><span data-stu-id="1be85-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1be85-140">Da die logischen und bitweisen Operatoren auf eine niedrigere Rangfolge als der anderen arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um die genaue Ausführung sicherzustellen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1be85-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="1be85-141">Z. B. 5 `Xor` 3 ist 6.</span><span class="sxs-lookup"><span data-stu-id="1be85-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="1be85-142">Um festzustellen, warum dies ist also in ihre binäre Darstellungen, 101 und 011 5 und 3 zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1be85-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="1be85-143">Klicken Sie dann anhand der vorherigen Tabelle ermitteln, ob 101 Xor 011 110, ist dies ist die binäre Darstellung der Dezimalzahl 6 ein.</span><span class="sxs-lookup"><span data-stu-id="1be85-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="1be85-144">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1be85-144">Data Types</span></span>  
 <span data-ttu-id="1be85-145">Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.</span><span class="sxs-lookup"><span data-stu-id="1be85-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="1be85-146">Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses wird die `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1be85-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="1be85-147">Einen bitweisen Vergleich, der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="1be85-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="1be85-148">Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="1be85-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1be85-149">Überladen</span><span class="sxs-lookup"><span data-stu-id="1be85-149">Overloading</span></span>  
 <span data-ttu-id="1be85-150">Die `Xor` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="1be85-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1be85-151">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet werden, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="1be85-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="1be85-152">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1be85-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be85-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1be85-153">Example</span></span>  
 <span data-ttu-id="1be85-154">Im folgenden Beispiel wird die `Xor` Operator zwei Ausdrücke logischen Ausschluss (exklusive logische Disjunktion) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1be85-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="1be85-155">Das Ergebnis ist eine `Boolean` -Wert, der angibt, ob genau einer der Ausdrücke ist `True`.</span><span class="sxs-lookup"><span data-stu-id="1be85-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="1be85-156">Das vorherige Beispiel erzeugt die Ergebnisse der `False`, `True`, und `False`bzw.</span><span class="sxs-lookup"><span data-stu-id="1be85-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be85-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1be85-157">Example</span></span>  
 <span data-ttu-id="1be85-158">Im folgenden Beispiel wird die `Xor` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken logischen Ausschluss (exklusive logische Disjunktion) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1be85-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="1be85-159">Das Bit im Ergebnismuster wird festgelegt, wenn genau eines der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1be85-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="1be85-160">Im vorherige Beispiel werden die Ergebnisse von 2, 12 und 14, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="1be85-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be85-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1be85-161">See also</span></span>
- [<span data-ttu-id="1be85-162">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1be85-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="1be85-163">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1be85-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1be85-164">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="1be85-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1be85-165">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1be85-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
