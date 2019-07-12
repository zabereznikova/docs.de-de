---
title: OrElse-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860144"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="e7d53-102">OrElse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7d53-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="e7d53-103">Führt eine verkürzte einschließende logischen Disjunktion zweier Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="e7d53-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7d53-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e7d53-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e7d53-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e7d53-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7d53-106">Required.</span></span> <span data-ttu-id="e7d53-107">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7d53-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="e7d53-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7d53-108">Required.</span></span> <span data-ttu-id="e7d53-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7d53-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e7d53-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e7d53-110">Required.</span></span> <span data-ttu-id="e7d53-111">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7d53-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7d53-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7d53-112">Remarks</span></span>  
 <span data-ttu-id="e7d53-113">Eine logische Operation gilt *kurzschließen* Wenn der kompilierte Code die Auswertung eines Ausdrucks je nach Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="e7d53-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="e7d53-114">Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit zum Auswerten des zweiten Ausdrucks, da das endgültige Ergebnis nicht mehr ändern können.</span><span class="sxs-lookup"><span data-stu-id="e7d53-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="e7d53-115">Das kurzschließen kann die Leistung verbessern, wenn der Ausdruck Umgangene komplex ist oder Prozeduraufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="e7d53-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="e7d53-116">Wenn eine oder beide Ausdrücke `True`, `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="e7d53-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="e7d53-117">In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="e7d53-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="e7d53-118">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="e7d53-118">If `expression1` is</span></span>|<span data-ttu-id="e7d53-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="e7d53-119">And `expression2` is</span></span>|<span data-ttu-id="e7d53-120">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="e7d53-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="e7d53-121">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="e7d53-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="e7d53-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e7d53-122">Data Types</span></span>  
 <span data-ttu-id="e7d53-123">Die `OrElse` Operator ist definiert, nur für die [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e7d53-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="e7d53-124">Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` vor der Auswertung des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="e7d53-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="e7d53-125">Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ, `False` wird `0` und `True` wird `-1`.</span><span class="sxs-lookup"><span data-stu-id="e7d53-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="e7d53-126">Weitere Informationen finden Sie unter [booleschen Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="e7d53-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="e7d53-127">Überladen</span><span class="sxs-lookup"><span data-stu-id="e7d53-127">Overloading</span></span>  
 <span data-ttu-id="e7d53-128">Die [oder-Operator](../../../visual-basic/language-reference/operators/or-operator.md) und [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur des Verhaltens neu definiert, wenn ein Operand den Typ dieser Klasse hat oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="e7d53-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e7d53-129">Das Überladen der `Or` und `IsTrue` Operatoren beeinflusst das Verhalten von der `OrElse` Operator.</span><span class="sxs-lookup"><span data-stu-id="e7d53-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="e7d53-130">Wenn Ihr Code verwendet `OrElse` für eine Klasse oder Struktur, die Überladungen `Or` und `IsTrue`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e7d53-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="e7d53-131">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e7d53-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7d53-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7d53-132">Example</span></span>  
 <span data-ttu-id="e7d53-133">Im folgenden Beispiel wird die `OrElse` Operator, um die logische Disjunktion zweier Ausdrücke ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7d53-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="e7d53-134">Das Ergebnis ist eine `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke "true".</span><span class="sxs-lookup"><span data-stu-id="e7d53-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="e7d53-135">Wenn der erste Ausdruck `True`, das zweite wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e7d53-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="e7d53-136">Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False` bzw.</span><span class="sxs-lookup"><span data-stu-id="e7d53-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="e7d53-137">Bei der Berechnung des `firstCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `True`.</span><span class="sxs-lookup"><span data-stu-id="e7d53-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="e7d53-138">Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung des `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="e7d53-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7d53-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7d53-139">Example</span></span>  
 <span data-ttu-id="e7d53-140">Das folgende Beispiel zeigt eine `If`... `Then` Anweisung, die zwei Prozeduraufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="e7d53-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="e7d53-141">Wenn der erste Aufruf gibt `True`, im zweite Verfahren wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e7d53-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="e7d53-142">Dies kann zu unerwarteten Ergebnissen führen, wenn das zweite Verfahren wichtige Aufgaben, die immer ausgeführt werden soll ausführt, wenn in diesem Abschnitt des Codes ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7d53-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="e7d53-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7d53-143">See also</span></span>

- [<span data-ttu-id="e7d53-144">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7d53-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="e7d53-145">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7d53-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e7d53-146">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e7d53-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e7d53-147">Or-Operator</span><span class="sxs-lookup"><span data-stu-id="e7d53-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="e7d53-148">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="e7d53-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="e7d53-149">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7d53-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
