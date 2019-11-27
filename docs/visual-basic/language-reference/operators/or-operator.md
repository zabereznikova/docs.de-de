---
title: Or-Operator
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
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348253"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="8aa3f-102">Or-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="8aa3f-103">Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8aa3f-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8aa3f-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="8aa3f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8aa3f-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8aa3f-106">Required.</span></span> <span data-ttu-id="8aa3f-107">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="8aa3f-108">Bei `Boolean` Vergleich ist `result` die inklusivlogische Disjunktion von zwei `Boolean`-Werten.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="8aa3f-109">Bei bitweisen Vorgängen ist `result` ein numerischer Wert, der die inklusive bitweise Disjunktion zweier numerischer Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8aa3f-110">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8aa3f-110">Required.</span></span> <span data-ttu-id="8aa3f-111">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8aa3f-112">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8aa3f-112">Required.</span></span> <span data-ttu-id="8aa3f-113">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8aa3f-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8aa3f-114">Remarks</span></span>  
 <span data-ttu-id="8aa3f-115">Für `Boolean` Vergleich ist `result` nur dann `False`, wenn sowohl `expression1` als auch `expression2` `False`ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="8aa3f-116">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8aa3f-117">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-117">If `expression1` is</span></span>|<span data-ttu-id="8aa3f-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-118">And `expression2` is</span></span>|<span data-ttu-id="8aa3f-119">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="8aa3f-120">Bei einem `Boolean` Vergleich wertet der `Or`-Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="8aa3f-121">Der [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *Kurzschluss*Vorgänge aus. Dies bedeutet, dass `expression2` nicht ausgewertet wird, wenn `expression1` `True`ist.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="8aa3f-122">Für bitweise Operationen führt der `Or` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8aa3f-123">Wenn Bit in `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-123">If bit in `expression1` is</span></span>|<span data-ttu-id="8aa3f-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-124">And bit in `expression2` is</span></span>|<span data-ttu-id="8aa3f-125">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="8aa3f-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="8aa3f-126">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-126">1</span></span>|<span data-ttu-id="8aa3f-127">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-127">1</span></span>|<span data-ttu-id="8aa3f-128">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-128">1</span></span>|  
|<span data-ttu-id="8aa3f-129">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-129">1</span></span>|<span data-ttu-id="8aa3f-130">0</span><span class="sxs-lookup"><span data-stu-id="8aa3f-130">0</span></span>|<span data-ttu-id="8aa3f-131">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-131">1</span></span>|  
|<span data-ttu-id="8aa3f-132">0</span><span class="sxs-lookup"><span data-stu-id="8aa3f-132">0</span></span>|<span data-ttu-id="8aa3f-133">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-133">1</span></span>|<span data-ttu-id="8aa3f-134">1</span><span class="sxs-lookup"><span data-stu-id="8aa3f-134">1</span></span>|  
|<span data-ttu-id="8aa3f-135">0</span><span class="sxs-lookup"><span data-stu-id="8aa3f-135">0</span></span>|<span data-ttu-id="8aa3f-136">0</span><span class="sxs-lookup"><span data-stu-id="8aa3f-136">0</span></span>|<span data-ttu-id="8aa3f-137">0</span><span class="sxs-lookup"><span data-stu-id="8aa3f-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8aa3f-138">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8aa3f-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8aa3f-139">Data Types</span></span>  
 <span data-ttu-id="8aa3f-140">Wenn die Operanden aus einem `Boolean` Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation aus.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="8aa3f-141">Für einen `Boolean` Vergleich ist der Datentyp des Ergebnisses `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8aa3f-142">Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="8aa3f-143">Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8aa3f-144">Überladen</span><span class="sxs-lookup"><span data-stu-id="8aa3f-144">Overloading</span></span>  
 <span data-ttu-id="8aa3f-145">Der `Or`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8aa3f-146">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8aa3f-147">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa3f-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8aa3f-148">Example</span></span>  
 <span data-ttu-id="8aa3f-149">Im folgenden Beispiel wird der `Or`-Operator verwendet, um eine inklusivlogische Disjunktion für zwei Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="8aa3f-150">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob einer der beiden Ausdrücke `True`ist.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="8aa3f-151">Das vorangehende Beispiel erzeugt die Ergebnisse der `True`, `True`und `False`.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa3f-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8aa3f-152">Example</span></span>  
 <span data-ttu-id="8aa3f-153">Im folgenden Beispiel wird der `Or`-Operator verwendet, um die inklusive logische Disjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="8aa3f-154">Das Bit im Ergebnis Muster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="8aa3f-155">Das vorherige Beispiel erzeugt die Ergebnisse von 10, 14 und 14.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa3f-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aa3f-156">See also</span></span>

- [<span data-ttu-id="8aa3f-157">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="8aa3f-158">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8aa3f-159">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8aa3f-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8aa3f-160">OrElse-Operator</span><span class="sxs-lookup"><span data-stu-id="8aa3f-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="8aa3f-161">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8aa3f-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
