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
ms.openlocfilehash: 70bbfef54d3f716e0e7463a39ee15e8480066695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603013"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="9c7ca-102">OrElse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7ca-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="9c7ca-103">Führt eine verkürzte einschließende logischen Disjunktion zweier Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c7ca-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9c7ca-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9c7ca-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9c7ca-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-106">Required.</span></span> <span data-ttu-id="9c7ca-107">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9c7ca-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-108">Required.</span></span> <span data-ttu-id="9c7ca-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9c7ca-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-110">Required.</span></span> <span data-ttu-id="9c7ca-111">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c7ca-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c7ca-112">Remarks</span></span>  
 <span data-ttu-id="9c7ca-113">Eine logische Operation gilt *kurzschließen* Wenn der kompilierte Code die Auswertung eines Ausdrucks je nach Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="9c7ca-114">Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit zum Auswerten des zweiten Ausdrucks, da das endgültige Ergebnis nicht mehr ändern können.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="9c7ca-115">Das kurzschließen kann die Leistung verbessern, wenn der Ausdruck Umgangene komplex ist oder Prozeduraufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="9c7ca-116">Wenn eine oder beide Ausdrücke `True`, `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="9c7ca-117">In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="9c7ca-118">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="9c7ca-118">If `expression1` is</span></span>|<span data-ttu-id="9c7ca-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="9c7ca-119">And `expression2` is</span></span>|<span data-ttu-id="9c7ca-120">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="9c7ca-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="9c7ca-121">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="9c7ca-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="9c7ca-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="9c7ca-122">Data Types</span></span>  
 <span data-ttu-id="9c7ca-123">Die `OrElse` Operator ist definiert, nur für die [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="9c7ca-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="9c7ca-124">Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="9c7ca-125">Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="9c7ca-126">Dies kann zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="9c7ca-127">Z. B. `5 OrElse 12` führt `–1` bei der Konvertierung in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9c7ca-128">Überladen</span><span class="sxs-lookup"><span data-stu-id="9c7ca-128">Overloading</span></span>  
 <span data-ttu-id="9c7ca-129">Die [oder-Operator](../../../visual-basic/language-reference/operators/or-operator.md) und [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur des Verhaltens neu definiert, wenn ein Operand den Typ dieser Klasse hat oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9c7ca-130">Das Überladen der `Or` und `IsTrue` Operatoren beeinflusst das Verhalten von der `OrElse` Operator.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="9c7ca-131">Wenn Ihr Code verwendet `OrElse` für eine Klasse oder Struktur, die Überladungen `Or` und `IsTrue`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="9c7ca-132">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9c7ca-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c7ca-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c7ca-133">Example</span></span>  
 <span data-ttu-id="9c7ca-134">Im folgenden Beispiel wird die `OrElse` Operator, um die logische Disjunktion zweier Ausdrücke ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="9c7ca-135">Das Ergebnis ist eine `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke "true".</span><span class="sxs-lookup"><span data-stu-id="9c7ca-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="9c7ca-136">Wenn der erste Ausdruck `True`, das zweite wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 <span data-ttu-id="9c7ca-137">Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False` bzw.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="9c7ca-138">Bei der Berechnung des `firstCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `True`.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="9c7ca-139">Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung des `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c7ca-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c7ca-140">Example</span></span>  
 <span data-ttu-id="9c7ca-141">Das folgende Beispiel zeigt eine `If`... `Then` Anweisung, die zwei Prozeduraufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="9c7ca-142">Wenn der erste Aufruf gibt `True`, im zweite Verfahren wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="9c7ca-143">Dies kann zu unerwarteten Ergebnissen führen, wenn das zweite Verfahren wichtige Aufgaben, die immer ausgeführt werden soll ausführt, wenn in diesem Abschnitt des Codes ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c7ca-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9c7ca-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c7ca-144">See also</span></span>
- [<span data-ttu-id="9c7ca-145">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7ca-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="9c7ca-146">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7ca-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9c7ca-147">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="9c7ca-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9c7ca-148">Or-Operator</span><span class="sxs-lookup"><span data-stu-id="9c7ca-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="9c7ca-149">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="9c7ca-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="9c7ca-150">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c7ca-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
