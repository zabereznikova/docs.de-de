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
ms.openlocfilehash: 8b67897956a21d06d465cf206856354d2e3f9d68
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371933"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="c30ad-102">AndAlso-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c30ad-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="c30ad-103">Führt eine kurze, logische Konjunktion zweier Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="c30ad-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c30ad-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c30ad-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="c30ad-105">Parts</span></span>  
  
|<span data-ttu-id="c30ad-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c30ad-106">Term</span></span>|<span data-ttu-id="c30ad-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c30ad-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="c30ad-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c30ad-108">Required.</span></span> <span data-ttu-id="c30ad-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c30ad-109">Any `Boolean` expression.</span></span> <span data-ttu-id="c30ad-110">Das Ergebnis ist das `Boolean` Ergebnis des Vergleichs der beiden Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c30ad-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="c30ad-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c30ad-111">Required.</span></span> <span data-ttu-id="c30ad-112">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c30ad-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="c30ad-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c30ad-113">Required.</span></span> <span data-ttu-id="c30ad-114">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c30ad-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c30ad-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c30ad-115">Remarks</span></span>  
 <span data-ttu-id="c30ad-116">Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="c30ad-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="c30ad-117">Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="c30ad-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="c30ad-118">Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.</span><span class="sxs-lookup"><span data-stu-id="c30ad-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="c30ad-119">Wenn beide Ausdrücke als ausgewertet `True` werden, `result` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="c30ad-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="c30ad-120">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c30ad-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c30ad-121">Wenn `expression1` gleich </span><span class="sxs-lookup"><span data-stu-id="c30ad-121">If `expression1` is</span></span>|<span data-ttu-id="c30ad-122">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="c30ad-122">And `expression2` is</span></span>|<span data-ttu-id="c30ad-123">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="c30ad-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="c30ad-124">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="c30ad-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="c30ad-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c30ad-125">Data Types</span></span>  
 <span data-ttu-id="c30ad-126">Der- `AndAlso` Operator ist nur für den [booleschen Datentyp](../data-types/boolean-data-type.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="c30ad-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="c30ad-127">Visual Basic konvertiert jeden Operanden nach Bedarf in, `Boolean` bevor der Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c30ad-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="c30ad-128">Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass zu `False` `0` und `True` wird `-1` .</span><span class="sxs-lookup"><span data-stu-id="c30ad-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="c30ad-129">Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="c30ad-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="c30ad-130">Überladen</span><span class="sxs-lookup"><span data-stu-id="c30ad-130">Overloading</span></span>  
 <span data-ttu-id="c30ad-131">Der [and-Operator](and-operator.md) und der [IsFalse-Operator](isfalse-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="c30ad-131">The [And Operator](and-operator.md) and the [IsFalse Operator](isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c30ad-132">Das überladen `And` der `IsFalse` Operatoren und wirkt sich auf das Verhalten des `AndAlso` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="c30ad-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="c30ad-133">Wenn Ihr Code `AndAlso` für eine Klasse oder Struktur verwendet, die und überlastet `And` `IsFalse` , sollten Sie sicher sein, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="c30ad-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="c30ad-134">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c30ad-134">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c30ad-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c30ad-135">Example</span></span>  
 <span data-ttu-id="c30ad-136">Im folgenden Beispiel wird der- `AndAlso` Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c30ad-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c30ad-137">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der gesamte zusammengefügten Ausdruck true ist.</span><span class="sxs-lookup"><span data-stu-id="c30ad-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="c30ad-138">Wenn der erste Ausdruck ist `False` , wird der zweite nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c30ad-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="c30ad-139">Im vorherigen Beispiel werden die Ergebnisse von `True` , `False` `False` bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c30ad-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="c30ad-140">Bei der Berechnung von `secondCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste bereits vorhanden ist `False` .</span><span class="sxs-lookup"><span data-stu-id="c30ad-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="c30ad-141">Der zweite Ausdruck wird jedoch in der Berechnung von ausgewertet `thirdCheck` .</span><span class="sxs-lookup"><span data-stu-id="c30ad-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c30ad-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c30ad-142">Example</span></span>  
 <span data-ttu-id="c30ad-143">Im folgenden Beispiel wird eine `Function` Prozedur gezeigt, die unter den Elementen eines Arrays nach einem angegebenen Wert sucht.</span><span class="sxs-lookup"><span data-stu-id="c30ad-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="c30ad-144">Wenn das Array leer ist oder die Array Länge überschritten wurde, `While` testet die Anweisung das Array Element nicht mit dem Suchwert.</span><span class="sxs-lookup"><span data-stu-id="c30ad-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="c30ad-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c30ad-145">See also</span></span>

- [<span data-ttu-id="c30ad-146">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c30ad-146">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="c30ad-147">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c30ad-147">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c30ad-148">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c30ad-148">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c30ad-149">And-Operator</span><span class="sxs-lookup"><span data-stu-id="c30ad-149">And Operator</span></span>](and-operator.md)
- [<span data-ttu-id="c30ad-150">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="c30ad-150">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="c30ad-151">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c30ad-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
