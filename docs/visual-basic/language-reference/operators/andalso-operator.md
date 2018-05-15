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
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="65859-102">AndAlso-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65859-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="65859-103">Führt eine verkürzte logischen Konjunktion zweier Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="65859-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65859-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65859-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="65859-105">Teile</span><span class="sxs-lookup"><span data-stu-id="65859-105">Parts</span></span>  
  
|<span data-ttu-id="65859-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="65859-106">Term</span></span>|<span data-ttu-id="65859-107">Definition</span><span class="sxs-lookup"><span data-stu-id="65859-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="65859-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="65859-108">Required.</span></span> <span data-ttu-id="65859-109">Beliebiger `Boolean`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="65859-109">Any `Boolean` expression.</span></span> <span data-ttu-id="65859-110">Das Ergebnis ist die `Boolean` Ergebnis des Vergleichs von zwei Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="65859-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="65859-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="65859-111">Required.</span></span> <span data-ttu-id="65859-112">Beliebiger `Boolean`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="65859-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="65859-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="65859-113">Required.</span></span> <span data-ttu-id="65859-114">Beliebiger `Boolean`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="65859-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65859-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65859-115">Remarks</span></span>  
 <span data-ttu-id="65859-116">Eine logische Operation gilt als *verkürzte* Wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="65859-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="65859-117">Wenn das Ergebnis des ersten Ausdrucks, ausgewertet über das endgültige Ergebnis des Vorgangs feststellt, besteht keine Notwendigkeit, der zweite Ausdruck ausgewertet werden, da das Endergebnis nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="65859-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="65859-118">Verkürzte kann die Leistung verbessern, wenn der umgehen Ausdruck komplex ist oder sie Prozeduraufrufe umfasst.</span><span class="sxs-lookup"><span data-stu-id="65859-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="65859-119">Wenn beide Ausdrücke `True`, `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="65859-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="65859-120">Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="65859-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="65859-121">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="65859-121">If `expression1` is</span></span>|<span data-ttu-id="65859-122">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="65859-122">And `expression2` is</span></span>|<span data-ttu-id="65859-123">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="65859-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="65859-124">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="65859-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="65859-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="65859-125">Data Types</span></span>  
 <span data-ttu-id="65859-126">Die `AndAlso` Operator definiert ist, nur für die [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="65859-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="65859-127">Visual Basic konvertiert jeden Operanden nach Bedarf `Boolean` und führt den Vorgang, die vollständig in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="65859-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="65859-128">Wenn Sie das Ergebnis in einen numerischen Typ zuweisen, konvertiert Visual Basic aus `Boolean` auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="65859-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="65859-129">Dies kann zu unerwartetem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="65859-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="65859-130">Beispielsweise `5 AndAlso 12` führt `–1` bei der Konvertierung in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="65859-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="65859-131">Überladen</span><span class="sxs-lookup"><span data-stu-id="65859-131">Overloading</span></span>  
 <span data-ttu-id="65859-132">Die [And-Operators](../../../visual-basic/language-reference/operators/and-operator.md) und die [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur ihr Verhalten definieren kann, wenn ein Operand den Typ dieses hat Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="65859-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="65859-133">Überladen der `And` und `IsFalse` Operatoren wirkt sich auf das Verhalten der `AndAlso` Operator.</span><span class="sxs-lookup"><span data-stu-id="65859-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="65859-134">Wenn im Code verwendet `AndAlso` auf eine Klasse oder Struktur, die Überladungen `And` und `IsFalse`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="65859-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="65859-135">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="65859-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="65859-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65859-136">Example</span></span>  
 <span data-ttu-id="65859-137">Im folgenden Beispiel wird die `AndAlso` Operator, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="65859-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="65859-138">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte verbundene Ausdruck true ist "true".</span><span class="sxs-lookup"><span data-stu-id="65859-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="65859-139">Wenn der erste Ausdruck ist `False`, die zweite wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="65859-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="65859-140">Das obige Beispiel erzeugt die Ergebnisse der `True`, `False`, und `False`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="65859-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="65859-141">Bei der Berechnung der `secondCheck`, der zweite Ausdruck nicht ausgewertet, da die erste bereits ist `False`.</span><span class="sxs-lookup"><span data-stu-id="65859-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="65859-142">Allerdings wird der zweite Ausdruck ausgewertet, bei der Berechnung der `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="65859-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65859-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65859-143">Example</span></span>  
 <span data-ttu-id="65859-144">Das folgende Beispiel zeigt eine `Function` Prozedur, die für einen bestimmten Wert zwischen den Elementen eines Arrays sucht.</span><span class="sxs-lookup"><span data-stu-id="65859-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="65859-145">Wenn das Array leer ist oder wenn die Länge des Arrays überschritten wurde, die `While` testet Anweisung keine Arrayelements mit dem Suchwert.</span><span class="sxs-lookup"><span data-stu-id="65859-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65859-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65859-146">See Also</span></span>  
 [<span data-ttu-id="65859-147">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65859-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="65859-148">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65859-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="65859-149">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="65859-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="65859-150">And-Operator</span><span class="sxs-lookup"><span data-stu-id="65859-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="65859-151">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="65859-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="65859-152">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65859-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
