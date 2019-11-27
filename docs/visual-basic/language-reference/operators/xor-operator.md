---
title: Xor-Operator
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
ms.openlocfilehash: c5c7ec87bc173f724f8c670395bc3b0458444df6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335410"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="b451d-102">Xor-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b451d-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="b451d-103">Führt einen logischen Ausschluss für zwei `Boolean` Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="b451d-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b451d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b451d-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="b451d-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="b451d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b451d-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b451d-106">Required.</span></span> <span data-ttu-id="b451d-107">Beliebige `Boolean` oder numerische Variable.</span><span class="sxs-lookup"><span data-stu-id="b451d-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="b451d-108">Bei einem booleschen Vergleich ist `result` der logische Ausschluss (exklusive logische Disjunktion) von zwei `Boolean` Werten.</span><span class="sxs-lookup"><span data-stu-id="b451d-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="b451d-109">Bei bitweisen Vorgängen ist `result` ein numerischer Wert, der den bitweisen Ausschluss (exklusive bitweise Disjunktion) von zwei numerischen Bitmustern darstellt.</span><span class="sxs-lookup"><span data-stu-id="b451d-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="b451d-110">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b451d-110">Required.</span></span> <span data-ttu-id="b451d-111">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b451d-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="b451d-112">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b451d-112">Required.</span></span> <span data-ttu-id="b451d-113">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b451d-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b451d-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b451d-114">Remarks</span></span>  
 <span data-ttu-id="b451d-115">Bei einem booleschen Vergleich wird `result` nur dann `True`, wenn genau eines `expression1` und `expression2` als `True`ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="b451d-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="b451d-116">Dies ist nur dann der Fall, wenn `expression1` und `expression2` als gegen `Boolean` Werte ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="b451d-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="b451d-117">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="b451d-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b451d-118">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-118">If `expression1` is</span></span>|<span data-ttu-id="b451d-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-119">And `expression2` is</span></span>|<span data-ttu-id="b451d-120">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="b451d-121">Bei einem booleschen Vergleich wertet der `Xor`-Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können.</span><span class="sxs-lookup"><span data-stu-id="b451d-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="b451d-122">Es gibt keinen Kurzschluss gegen `Xor`, da das Ergebnis immer von beiden Operanden abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="b451d-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="b451d-123">Informationen zu *kurzen Schluss* logischen Operatoren finden Sie unter [andgleich-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b451d-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="b451d-124">Für bitweise Operationen führt der `Xor` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="b451d-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="b451d-125">Wenn Bit in `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-125">If bit in `expression1` is</span></span>|<span data-ttu-id="b451d-126">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-126">And bit in `expression2` is</span></span>|<span data-ttu-id="b451d-127">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="b451d-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="b451d-128">1</span><span class="sxs-lookup"><span data-stu-id="b451d-128">1</span></span>|<span data-ttu-id="b451d-129">1</span><span class="sxs-lookup"><span data-stu-id="b451d-129">1</span></span>|<span data-ttu-id="b451d-130">0</span><span class="sxs-lookup"><span data-stu-id="b451d-130">0</span></span>|  
|<span data-ttu-id="b451d-131">1</span><span class="sxs-lookup"><span data-stu-id="b451d-131">1</span></span>|<span data-ttu-id="b451d-132">0</span><span class="sxs-lookup"><span data-stu-id="b451d-132">0</span></span>|<span data-ttu-id="b451d-133">1</span><span class="sxs-lookup"><span data-stu-id="b451d-133">1</span></span>|  
|<span data-ttu-id="b451d-134">0</span><span class="sxs-lookup"><span data-stu-id="b451d-134">0</span></span>|<span data-ttu-id="b451d-135">1</span><span class="sxs-lookup"><span data-stu-id="b451d-135">1</span></span>|<span data-ttu-id="b451d-136">1</span><span class="sxs-lookup"><span data-stu-id="b451d-136">1</span></span>|  
|<span data-ttu-id="b451d-137">0</span><span class="sxs-lookup"><span data-stu-id="b451d-137">0</span></span>|<span data-ttu-id="b451d-138">0</span><span class="sxs-lookup"><span data-stu-id="b451d-138">0</span></span>|<span data-ttu-id="b451d-139">0</span><span class="sxs-lookup"><span data-stu-id="b451d-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b451d-140">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b451d-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="b451d-141">Beispielsweise ist der Wert für 5 `Xor` 3 6.</span><span class="sxs-lookup"><span data-stu-id="b451d-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="b451d-142">Um zu sehen, warum dies der Fall ist, konvertieren Sie 5 und 3 in die Binär Darstellungen 101 und 011.</span><span class="sxs-lookup"><span data-stu-id="b451d-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="b451d-143">Verwenden Sie dann die vorherige Tabelle, um zu bestimmen, dass 101 Xor 011 110 ist, was die binäre Darstellung der Dezimalzahl 6 ist.</span><span class="sxs-lookup"><span data-stu-id="b451d-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b451d-144">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b451d-144">Data Types</span></span>  
 <span data-ttu-id="b451d-145">Wenn die Operanden aus einem `Boolean` Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation aus.</span><span class="sxs-lookup"><span data-stu-id="b451d-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="b451d-146">Für einen `Boolean` Vergleich ist der Datentyp des Ergebnisses `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b451d-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="b451d-147">Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="b451d-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="b451d-148">Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="b451d-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b451d-149">Überladen</span><span class="sxs-lookup"><span data-stu-id="b451d-149">Overloading</span></span>  
 <span data-ttu-id="b451d-150">Der `Xor`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="b451d-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b451d-151">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="b451d-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="b451d-152">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b451d-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b451d-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b451d-153">Example</span></span>  
 <span data-ttu-id="b451d-154">Im folgenden Beispiel wird der `Xor`-Operator verwendet, um einen logischen Ausschluss (exklusive logische Disjunktion) für zwei Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b451d-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="b451d-155">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob genau einer der Ausdrücke `True`ist.</span><span class="sxs-lookup"><span data-stu-id="b451d-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="b451d-156">Im vorherigen Beispiel werden Ergebnisse von `False`, `True`und `False`erstellt.</span><span class="sxs-lookup"><span data-stu-id="b451d-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b451d-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b451d-157">Example</span></span>  
 <span data-ttu-id="b451d-158">Im folgenden Beispiel wird der `Xor`-Operator verwendet, um einen logischen Ausschluss (exklusive logische Disjunktion) für die einzelnen Bits zweier numerischer Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b451d-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="b451d-159">Das Bit im Ergebnis Muster wird festgelegt, wenn genau eines der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b451d-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="b451d-160">Im vorherigen Beispiel werden die Ergebnisse 2, 12 bzw. 14 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b451d-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b451d-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b451d-161">See also</span></span>

- [<span data-ttu-id="b451d-162">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b451d-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="b451d-163">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b451d-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b451d-164">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b451d-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b451d-165">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b451d-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
