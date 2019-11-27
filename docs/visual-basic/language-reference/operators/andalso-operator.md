---
title: AndAlso-Operator
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
ms.openlocfilehash: b3801c7e05142e1bc793e3c9d49a6f6991756f9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350235"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="41232-102">AndAlso-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41232-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="41232-103">Führt eine kurze, logische Konjunktion zweier Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="41232-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41232-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41232-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="41232-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="41232-105">Parts</span></span>  
  
|<span data-ttu-id="41232-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="41232-106">Term</span></span>|<span data-ttu-id="41232-107">Definition</span><span class="sxs-lookup"><span data-stu-id="41232-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="41232-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="41232-108">Required.</span></span> <span data-ttu-id="41232-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="41232-109">Any `Boolean` expression.</span></span> <span data-ttu-id="41232-110">Das Ergebnis ist das `Boolean` Ergebnis des Vergleichs der beiden Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="41232-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="41232-111">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="41232-111">Required.</span></span> <span data-ttu-id="41232-112">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="41232-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="41232-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="41232-113">Required.</span></span> <span data-ttu-id="41232-114">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="41232-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41232-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41232-115">Remarks</span></span>  
 <span data-ttu-id="41232-116">Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="41232-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="41232-117">Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="41232-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="41232-118">Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.</span><span class="sxs-lookup"><span data-stu-id="41232-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="41232-119">Wenn beide Ausdrücke als `True`ausgewertet werden, wird `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="41232-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="41232-120">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="41232-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="41232-121">Wenn `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="41232-121">If `expression1` is</span></span>|<span data-ttu-id="41232-122">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="41232-122">And `expression2` is</span></span>|<span data-ttu-id="41232-123">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="41232-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="41232-124">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="41232-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="41232-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="41232-125">Data Types</span></span>  
 <span data-ttu-id="41232-126">Der `AndAlso`-Operator ist nur für den [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="41232-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="41232-127">Visual Basic konvertiert jeden Operanden nach Bedarf in `Boolean`, bevor der Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="41232-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="41232-128">Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass `False` `0` werden und `True` `-1`wird.</span><span class="sxs-lookup"><span data-stu-id="41232-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="41232-129">Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="41232-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="41232-130">Überladen</span><span class="sxs-lookup"><span data-stu-id="41232-130">Overloading</span></span>  
 <span data-ttu-id="41232-131">Der [and-Operator](../../../visual-basic/language-reference/operators/and-operator.md) und der [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="41232-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="41232-132">Das Überladen der Operatoren `And` und `IsFalse` wirkt sich auf das Verhalten des `AndAlso` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="41232-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="41232-133">Wenn Ihr Code `AndAlso` für eine Klasse oder Struktur verwendet, die `And` und `IsFalse`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="41232-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="41232-134">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="41232-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41232-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41232-135">Example</span></span>  
 <span data-ttu-id="41232-136">Im folgenden Beispiel wird der `AndAlso`-Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="41232-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="41232-137">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte zusammengefügten Ausdruck true ist.</span><span class="sxs-lookup"><span data-stu-id="41232-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="41232-138">Wenn der erste Ausdruck `False`ist, wird der zweite nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="41232-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="41232-139">Das vorangehende Beispiel erzeugt die Ergebnisse der `True`, `False`und `False`.</span><span class="sxs-lookup"><span data-stu-id="41232-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="41232-140">Bei der Berechnung der `secondCheck`wird der zweite Ausdruck nicht ausgewertet, da der erste bereits `False`ist.</span><span class="sxs-lookup"><span data-stu-id="41232-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="41232-141">Der zweite Ausdruck wird jedoch in der Berechnung der `thirdCheck`ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="41232-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41232-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41232-142">Example</span></span>  
 <span data-ttu-id="41232-143">Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die in den Elementen eines Arrays nach einem angegebenen Wert sucht.</span><span class="sxs-lookup"><span data-stu-id="41232-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="41232-144">Wenn das Array leer ist oder die Array Länge überschritten wurde, testet die `While`-Anweisung das Array Element nicht mit dem Suchwert.</span><span class="sxs-lookup"><span data-stu-id="41232-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="41232-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41232-145">See also</span></span>

- [<span data-ttu-id="41232-146">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41232-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="41232-147">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41232-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="41232-148">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="41232-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="41232-149">And-Operator</span><span class="sxs-lookup"><span data-stu-id="41232-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="41232-150">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="41232-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="41232-151">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41232-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
