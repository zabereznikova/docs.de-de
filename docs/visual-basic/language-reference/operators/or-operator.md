---
title: Or-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 9e02f619a81ee3c15321dfd44963c1a7d29843ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="bf457-102">Or-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf457-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="bf457-103">Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="bf457-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf457-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf457-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="bf457-105">Teile</span><span class="sxs-lookup"><span data-stu-id="bf457-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="bf457-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf457-106">Required.</span></span> <span data-ttu-id="bf457-107">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bf457-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="bf457-108">Für `Boolean` Vergleich `result` ist die inklusive logische Disjunktion zweier `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="bf457-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="bf457-109">Für bitweise Operationen `result` ist ein numerischer Wert, der die inklusive bitweise Disjunktion von zwei numerischen Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="bf457-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="bf457-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf457-110">Required.</span></span> <span data-ttu-id="bf457-111">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bf457-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="bf457-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf457-112">Required.</span></span> <span data-ttu-id="bf457-113">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bf457-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf457-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf457-114">Remarks</span></span>  
 <span data-ttu-id="bf457-115">Für `Boolean` Vergleich `result` ist `False` Wenn und nur wenn beide `expression1` und `expression2` ergeben `False`.</span><span class="sxs-lookup"><span data-stu-id="bf457-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="bf457-116">Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="bf457-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="bf457-117">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-117">If `expression1` is</span></span>|<span data-ttu-id="bf457-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-118">And `expression2` is</span></span>|<span data-ttu-id="bf457-119">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="bf457-120">In einer `Boolean` Vergleich der `Or` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bf457-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="bf457-121">Die [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *verkürzte*, was bedeutet, dass bei `expression1` ist `True`, klicken Sie dann `expression2` wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bf457-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="bf457-122">Für bitweise Operationen der `Or` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bf457-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="bf457-123">Wenn bit `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-123">If bit in `expression1` is</span></span>|<span data-ttu-id="bf457-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-124">And bit in `expression2` is</span></span>|<span data-ttu-id="bf457-125">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="bf457-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="bf457-126">1</span><span class="sxs-lookup"><span data-stu-id="bf457-126">1</span></span>|<span data-ttu-id="bf457-127">1</span><span class="sxs-lookup"><span data-stu-id="bf457-127">1</span></span>|<span data-ttu-id="bf457-128">1</span><span class="sxs-lookup"><span data-stu-id="bf457-128">1</span></span>|  
|<span data-ttu-id="bf457-129">1</span><span class="sxs-lookup"><span data-stu-id="bf457-129">1</span></span>|<span data-ttu-id="bf457-130">0</span><span class="sxs-lookup"><span data-stu-id="bf457-130">0</span></span>|<span data-ttu-id="bf457-131">1</span><span class="sxs-lookup"><span data-stu-id="bf457-131">1</span></span>|  
|<span data-ttu-id="bf457-132">0</span><span class="sxs-lookup"><span data-stu-id="bf457-132">0</span></span>|<span data-ttu-id="bf457-133">1</span><span class="sxs-lookup"><span data-stu-id="bf457-133">1</span></span>|<span data-ttu-id="bf457-134">1</span><span class="sxs-lookup"><span data-stu-id="bf457-134">1</span></span>|  
|<span data-ttu-id="bf457-135">0</span><span class="sxs-lookup"><span data-stu-id="bf457-135">0</span></span>|<span data-ttu-id="bf457-136">0</span><span class="sxs-lookup"><span data-stu-id="bf457-136">0</span></span>|<span data-ttu-id="bf457-137">0</span><span class="sxs-lookup"><span data-stu-id="bf457-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bf457-138">Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bf457-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="bf457-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="bf457-139">Data Types</span></span>  
 <span data-ttu-id="bf457-140">Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.</span><span class="sxs-lookup"><span data-stu-id="bf457-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="bf457-141">Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="bf457-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="bf457-142">Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="bf457-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="bf457-143">Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="bf457-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="bf457-144">Überladen</span><span class="sxs-lookup"><span data-stu-id="bf457-144">Overloading</span></span>  
 <span data-ttu-id="bf457-145">Die `Or` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="bf457-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bf457-146">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="bf457-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bf457-147">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bf457-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf457-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf457-148">Example</span></span>  
 <span data-ttu-id="bf457-149">Im folgenden Beispiel wird die `Or` Operator, um eine inklusive logische Disjunktion zweier Ausdrücke ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf457-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="bf457-150">Das Ergebnis ist ein `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke `True`.</span><span class="sxs-lookup"><span data-stu-id="bf457-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 <span data-ttu-id="bf457-151">Das obige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bf457-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf457-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf457-152">Example</span></span>  
 <span data-ttu-id="bf457-153">Im folgenden Beispiel wird die `Or` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken inklusiven logische Disjunktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf457-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="bf457-154">Das Bit im Ergebnismuster wird festgelegt, wenn entweder der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bf457-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 <span data-ttu-id="bf457-155">Im vorherige Beispiel werden die Ergebnisse von 10, 14 und 14, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="bf457-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf457-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf457-156">See Also</span></span>  
 [<span data-ttu-id="bf457-157">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf457-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="bf457-158">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf457-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="bf457-159">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="bf457-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="bf457-160">OrElse-Operator</span><span class="sxs-lookup"><span data-stu-id="bf457-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [<span data-ttu-id="bf457-161">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf457-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
