---
title: AndAlso-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: c9f4d9c880e189eb0ad4834736bdc664eb5b4376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703561"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="fb9dc-102">AndAlso-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb9dc-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="fb9dc-103">Führt eine verkürzte logischen Konjunktion zweier Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb9dc-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="fb9dc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="fb9dc-105">Parts</span></span>  
  
|<span data-ttu-id="fb9dc-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="fb9dc-106">Term</span></span>|<span data-ttu-id="fb9dc-107">Definition</span><span class="sxs-lookup"><span data-stu-id="fb9dc-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="fb9dc-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-108">Required.</span></span> <span data-ttu-id="fb9dc-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-109">Any `Boolean` expression.</span></span> <span data-ttu-id="fb9dc-110">Das Ergebnis ist die `Boolean` Ergebnis des Vergleichs zwischen zwei Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="fb9dc-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-111">Required.</span></span> <span data-ttu-id="fb9dc-112">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="fb9dc-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-113">Required.</span></span> <span data-ttu-id="fb9dc-114">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb9dc-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb9dc-115">Remarks</span></span>  
 <span data-ttu-id="fb9dc-116">Eine logische Operation gilt *kurzschließen* Wenn der kompilierte Code die Auswertung eines Ausdrucks je nach Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="fb9dc-117">Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit zum Auswerten des zweiten Ausdrucks, da das endgültige Ergebnis nicht mehr ändern können.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="fb9dc-118">Das kurzschließen kann die Leistung verbessern, wenn der Ausdruck Umgangene komplex ist oder Prozeduraufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="fb9dc-119">Wenn beide Ausdrücke `True`, `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="fb9dc-120">In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="fb9dc-121">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="fb9dc-121">If `expression1` is</span></span>|<span data-ttu-id="fb9dc-122">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="fb9dc-122">And `expression2` is</span></span>|<span data-ttu-id="fb9dc-123">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="fb9dc-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="fb9dc-124">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="fb9dc-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="fb9dc-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="fb9dc-125">Data Types</span></span>  
 <span data-ttu-id="fb9dc-126">Die `AndAlso` Operator ist definiert, nur für die [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="fb9dc-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="fb9dc-127">Visual Basic konvertiert alle Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="fb9dc-128">Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="fb9dc-129">Dies kann zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="fb9dc-130">Z. B. `5 AndAlso 12` führt `–1` bei der Konvertierung in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fb9dc-131">Überladen</span><span class="sxs-lookup"><span data-stu-id="fb9dc-131">Overloading</span></span>  
 <span data-ttu-id="fb9dc-132">Die [und Operator](../../../visual-basic/language-reference/operators/and-operator.md) und [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur des Verhaltens neu definiert, wenn ein Operand den Typ des, hat Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fb9dc-133">Das Überladen der `And` und `IsFalse` Operatoren beeinflusst das Verhalten von der `AndAlso` Operator.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="fb9dc-134">Wenn Ihr Code verwendet `AndAlso` für eine Klasse oder Struktur, die Überladungen `And` und `IsFalse`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="fb9dc-135">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fb9dc-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb9dc-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb9dc-136">Example</span></span>  
 <span data-ttu-id="fb9dc-137">Im folgenden Beispiel wird die `AndAlso` Operator, um eine logische Konjunktion zweier Ausdrücke ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="fb9dc-138">Das Ergebnis ist eine `Boolean` Wert, der angibt, ob die gesamte verbundene Ausdruck true ist "true".</span><span class="sxs-lookup"><span data-stu-id="fb9dc-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="fb9dc-139">Wenn der erste Ausdruck `False`, das zweite wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="fb9dc-140">Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `False`, und `False`bzw.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="fb9dc-141">Bei der Berechnung des `secondCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `False`.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="fb9dc-142">Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung des `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb9dc-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb9dc-143">Example</span></span>  
 <span data-ttu-id="fb9dc-144">Das folgende Beispiel zeigt eine `Function` Prozedur, die für einen bestimmten Wert zwischen den Elementen eines Arrays sucht.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="fb9dc-145">Wenn das Array leer ist oder wenn die Länge des Arrays überschritten wurde, die `While` -Anweisung ist nicht das Array-Element für den zu suchenden Wert testen.</span><span class="sxs-lookup"><span data-stu-id="fb9dc-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fb9dc-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb9dc-146">See also</span></span>
- [<span data-ttu-id="fb9dc-147">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb9dc-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="fb9dc-148">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb9dc-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fb9dc-149">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="fb9dc-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fb9dc-150">And-Operator</span><span class="sxs-lookup"><span data-stu-id="fb9dc-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="fb9dc-151">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="fb9dc-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="fb9dc-152">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb9dc-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
