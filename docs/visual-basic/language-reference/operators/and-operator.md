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
ms.openlocfilehash: bd6ebbf5f53a7cf187b5d8ce7630080d44d46df2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591620"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="f0ac4-102">And-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ac4-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="f0ac4-103">Führt eine logische Konjunktion zweier `Boolean`-Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ac4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0ac4-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="f0ac4-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f0ac4-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f0ac4-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-106">Required.</span></span> <span data-ttu-id="f0ac4-107">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="f0ac4-108">Bei einem booleschen Vergleich ist `result` die logische Verknüpfung von zwei `Boolean`-Werten.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="f0ac4-109">Bei bitweisen Vorgängen ist `result` ein numerischer Wert, der die bitweise Konjunktion zweier numerischer Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="f0ac4-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-110">Required.</span></span> <span data-ttu-id="f0ac4-111">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="f0ac4-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-112">Required.</span></span> <span data-ttu-id="f0ac4-113">Ein `Boolean` beliebiger oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ac4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0ac4-114">Remarks</span></span>  
 <span data-ttu-id="f0ac4-115">Bei einem booleschen Vergleich ist `result` nur dann `True`, wenn sowohl `expression1` als auch `expression2` zu `True` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="f0ac4-116">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f0ac4-117">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-117">If `expression1` is</span></span>|<span data-ttu-id="f0ac4-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-118">And `expression2` is</span></span>|<span data-ttu-id="f0ac4-119">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="f0ac4-120">Bei einem booleschen Vergleich wertet der `And`-Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="f0ac4-121">Der [andwas-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression2` nicht ausgewertet wird, wenn `expression1` `False` ist.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="f0ac4-122">Beim Anwenden auf numerische Werte führt der `And`-Operator einen bitweisen Vergleich identischer positionierter Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f0ac4-123">Wenn Bit in `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-123">If bit in `expression1` is</span></span>|<span data-ttu-id="f0ac4-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-124">And bit in `expression2` is</span></span>|<span data-ttu-id="f0ac4-125">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="f0ac4-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="f0ac4-126">1</span><span class="sxs-lookup"><span data-stu-id="f0ac4-126">1</span></span>|<span data-ttu-id="f0ac4-127">1</span><span class="sxs-lookup"><span data-stu-id="f0ac4-127">1</span></span>|<span data-ttu-id="f0ac4-128">1</span><span class="sxs-lookup"><span data-stu-id="f0ac4-128">1</span></span>|  
|<span data-ttu-id="f0ac4-129">1</span><span class="sxs-lookup"><span data-stu-id="f0ac4-129">1</span></span>|<span data-ttu-id="f0ac4-130">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-130">0</span></span>|<span data-ttu-id="f0ac4-131">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-131">0</span></span>|  
|<span data-ttu-id="f0ac4-132">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-132">0</span></span>|<span data-ttu-id="f0ac4-133">1</span><span class="sxs-lookup"><span data-stu-id="f0ac4-133">1</span></span>|<span data-ttu-id="f0ac4-134">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-134">0</span></span>|  
|<span data-ttu-id="f0ac4-135">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-135">0</span></span>|<span data-ttu-id="f0ac4-136">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-136">0</span></span>|<span data-ttu-id="f0ac4-137">0</span><span class="sxs-lookup"><span data-stu-id="f0ac4-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f0ac4-138">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um genaue Ergebnisse sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f0ac4-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="f0ac4-139">Data Types</span></span>  
 <span data-ttu-id="f0ac4-140">Wenn die Operanden aus einem `Boolean`-Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean`-Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise-Operation aus.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="f0ac4-141">Bei einem booleschen Vergleich ist der Datentyp des Ergebnisses `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f0ac4-142">Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2` geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="f0ac4-143">Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac4-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0ac4-144">Der `And`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f0ac4-145">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f0ac4-146">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac4-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ac4-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0ac4-147">Example</span></span>  
 <span data-ttu-id="f0ac4-148">Im folgenden Beispiel wird der `And`-Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="f0ac4-149">Das Ergebnis ist ein `Boolean`-Wert, der angibt, ob beide Ausdrücke `True` sind.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="f0ac4-150">Im vorangehenden Beispiel werden Ergebnisse von `True` bzw. `False` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ac4-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0ac4-151">Example</span></span>  
 <span data-ttu-id="f0ac4-152">Im folgenden Beispiel wird der `And`-Operator verwendet, um eine logische Konjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="f0ac4-153">Das Bit im Ergebnis Muster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="f0ac4-154">Im vorherigen Beispiel werden die Ergebnisse von 8, 2 bzw. 0 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f0ac4-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ac4-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0ac4-155">See also</span></span>

- [<span data-ttu-id="f0ac4-156">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ac4-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="f0ac4-157">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ac4-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f0ac4-158">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="f0ac4-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f0ac4-159">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="f0ac4-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="f0ac4-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0ac4-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
