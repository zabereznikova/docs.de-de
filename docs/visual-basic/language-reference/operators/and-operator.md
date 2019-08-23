---
title: And-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
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
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913171"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="397e6-102">And-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="397e6-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="397e6-103">Führt eine logische Konjunktion zweier `Boolean` Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="397e6-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="397e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="397e6-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="397e6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="397e6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="397e6-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="397e6-106">Required.</span></span> <span data-ttu-id="397e6-107">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="397e6-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="397e6-108">Bei einem booleschen Vergleich `result` ist die logische Verknüpfung von zwei `Boolean` Werten.</span><span class="sxs-lookup"><span data-stu-id="397e6-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="397e6-109">Für bitweise Vorgänge ist ein `result` numerischer Wert, der die bitweise Konjunktion zweier numerischer Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="397e6-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="397e6-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="397e6-110">Required.</span></span> <span data-ttu-id="397e6-111">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="397e6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="397e6-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="397e6-112">Required.</span></span> <span data-ttu-id="397e6-113">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="397e6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="397e6-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="397e6-114">Remarks</span></span>  
 <span data-ttu-id="397e6-115">Bei einem booleschen Vergleich `result` ist `True` nur dann, wenn sowohl `expression1` als `expression2` auch als `True`ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="397e6-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="397e6-116">In der folgenden Tabelle wird `result` veranschaulicht, wie bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="397e6-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="397e6-117">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="397e6-117">If `expression1` is</span></span>|<span data-ttu-id="397e6-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="397e6-118">And `expression2` is</span></span>|<span data-ttu-id="397e6-119">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="397e6-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="397e6-120">Bei einem booleschen Vergleich wertet der `And` Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können.</span><span class="sxs-lookup"><span data-stu-id="397e6-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="397e6-121">Der [andwas-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression1` , `False`wenn ist `expression2` , nicht ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="397e6-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="397e6-122">Beim Anwenden auf numerische Werte führt der `And` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken aus und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="397e6-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="397e6-123">Wenn Bit in `expression1`</span><span class="sxs-lookup"><span data-stu-id="397e6-123">If bit in `expression1` is</span></span>|<span data-ttu-id="397e6-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="397e6-124">And bit in `expression2` is</span></span>|<span data-ttu-id="397e6-125">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="397e6-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="397e6-126">1</span><span class="sxs-lookup"><span data-stu-id="397e6-126">1</span></span>|<span data-ttu-id="397e6-127">1</span><span class="sxs-lookup"><span data-stu-id="397e6-127">1</span></span>|<span data-ttu-id="397e6-128">1</span><span class="sxs-lookup"><span data-stu-id="397e6-128">1</span></span>|  
|<span data-ttu-id="397e6-129">1</span><span class="sxs-lookup"><span data-stu-id="397e6-129">1</span></span>|<span data-ttu-id="397e6-130">0</span><span class="sxs-lookup"><span data-stu-id="397e6-130">0</span></span>|<span data-ttu-id="397e6-131">0</span><span class="sxs-lookup"><span data-stu-id="397e6-131">0</span></span>|  
|<span data-ttu-id="397e6-132">0</span><span class="sxs-lookup"><span data-stu-id="397e6-132">0</span></span>|<span data-ttu-id="397e6-133">1</span><span class="sxs-lookup"><span data-stu-id="397e6-133">1</span></span>|<span data-ttu-id="397e6-134">0</span><span class="sxs-lookup"><span data-stu-id="397e6-134">0</span></span>|  
|<span data-ttu-id="397e6-135">0</span><span class="sxs-lookup"><span data-stu-id="397e6-135">0</span></span>|<span data-ttu-id="397e6-136">0</span><span class="sxs-lookup"><span data-stu-id="397e6-136">0</span></span>|<span data-ttu-id="397e6-137">0</span><span class="sxs-lookup"><span data-stu-id="397e6-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="397e6-138">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um genaue Ergebnisse sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="397e6-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="397e6-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="397e6-139">Data Types</span></span>  
 <span data-ttu-id="397e6-140">Wenn die `Boolean` Operanden aus einem Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation aus.</span><span class="sxs-lookup"><span data-stu-id="397e6-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="397e6-141">Bei einem booleschen Vergleich ist `Boolean`der Datentyp des Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="397e6-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="397e6-142">Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="397e6-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="397e6-143">Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="397e6-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="397e6-144">Der `And` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="397e6-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="397e6-145">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="397e6-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="397e6-146">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="397e6-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="397e6-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="397e6-147">Example</span></span>  
 <span data-ttu-id="397e6-148">Im folgenden Beispiel wird der `And` -Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="397e6-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="397e6-149">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob beide Ausdrücke sind `True`.</span><span class="sxs-lookup"><span data-stu-id="397e6-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="397e6-150">Das vorherige Beispiel erzeugt die Ergebnisse `True` von `False`und.</span><span class="sxs-lookup"><span data-stu-id="397e6-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="397e6-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="397e6-151">Example</span></span>  
 <span data-ttu-id="397e6-152">Im folgenden Beispiel wird der `And` -Operator verwendet, um eine logische Konjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="397e6-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="397e6-153">Das Bit im Ergebnis Muster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="397e6-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="397e6-154">Im vorherigen Beispiel werden die Ergebnisse von 8, 2 bzw. 0 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="397e6-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397e6-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="397e6-155">See also</span></span>

- [<span data-ttu-id="397e6-156">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="397e6-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="397e6-157">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="397e6-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="397e6-158">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="397e6-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="397e6-159">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="397e6-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="397e6-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="397e6-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
