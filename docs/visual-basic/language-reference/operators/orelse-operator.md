---
title: OrElse-Operator
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
ms.openlocfilehash: 3095a11523eeb8ec531c7f312fca74d2a070c92f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401406"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="ce001-102">OrElse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce001-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="ce001-103">Führt eine kurze, inklusive logische Disjunktion für zwei Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="ce001-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce001-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce001-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ce001-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="ce001-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ce001-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce001-106">Required.</span></span> <span data-ttu-id="ce001-107">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce001-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="ce001-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce001-108">Required.</span></span> <span data-ttu-id="ce001-109">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce001-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ce001-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce001-110">Required.</span></span> <span data-ttu-id="ce001-111">Beliebiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce001-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce001-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce001-112">Remarks</span></span>  
 <span data-ttu-id="ce001-113">Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="ce001-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="ce001-114">Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="ce001-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="ce001-115">Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.</span><span class="sxs-lookup"><span data-stu-id="ce001-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="ce001-116">Wenn mindestens einer der Ausdrücke als ausgewertet wird `True` , `result` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="ce001-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="ce001-117">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="ce001-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="ce001-118">Wenn `expression1` gleich </span><span class="sxs-lookup"><span data-stu-id="ce001-118">If `expression1` is</span></span>|<span data-ttu-id="ce001-119">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="ce001-119">And `expression2` is</span></span>|<span data-ttu-id="ce001-120">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="ce001-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="ce001-121">(nicht ausgewertet)</span><span class="sxs-lookup"><span data-stu-id="ce001-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="ce001-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ce001-122">Data Types</span></span>  
 <span data-ttu-id="ce001-123">Der- `OrElse` Operator ist nur für den [booleschen Datentyp](../data-types/boolean-data-type.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="ce001-123">The `OrElse` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="ce001-124">Visual Basic konvertiert jeden Operanden nach Bedarf in, `Boolean` bevor der Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ce001-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="ce001-125">Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass zu `False` `0` und `True` wird `-1` .</span><span class="sxs-lookup"><span data-stu-id="ce001-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="ce001-126">Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="ce001-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="ce001-127">Überladen</span><span class="sxs-lookup"><span data-stu-id="ce001-127">Overloading</span></span>  
 <span data-ttu-id="ce001-128">Der [OR-Operator](or-operator.md) und der [IsTrue-Operator](istrue-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="ce001-128">The [Or Operator](or-operator.md) and the [IsTrue Operator](istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ce001-129">Das überladen `Or` der `IsTrue` Operatoren und wirkt sich auf das Verhalten des `OrElse` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="ce001-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="ce001-130">Wenn Ihr Code `OrElse` für eine Klasse oder Struktur verwendet, die und überlastet `Or` `IsTrue` , sollten Sie sicher sein, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="ce001-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="ce001-131">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ce001-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce001-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce001-132">Example</span></span>  
 <span data-ttu-id="ce001-133">Im folgenden Beispiel wird der- `OrElse` Operator verwendet, um eine logische Disjunktion für zwei Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ce001-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="ce001-134">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob einer der beiden Ausdrücke True ist.</span><span class="sxs-lookup"><span data-stu-id="ce001-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="ce001-135">Wenn der erste Ausdruck ist `True` , wird der zweite nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ce001-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="ce001-136">Das vorangehende Beispiel erzeugt die Ergebnisse von `True` , `True` `False` bzw.</span><span class="sxs-lookup"><span data-stu-id="ce001-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="ce001-137">Bei der Berechnung von `firstCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste bereits vorhanden ist `True` .</span><span class="sxs-lookup"><span data-stu-id="ce001-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="ce001-138">Der zweite Ausdruck wird jedoch in der Berechnung von ausgewertet `secondCheck` .</span><span class="sxs-lookup"><span data-stu-id="ce001-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce001-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce001-139">Example</span></span>  
 <span data-ttu-id="ce001-140">Das folgende Beispiel zeigt eine `If` ...-Anweisung, die `Then` zwei Prozedur Aufrufe enthält.</span><span class="sxs-lookup"><span data-stu-id="ce001-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="ce001-141">Wenn der erste Aufruf zurückgegeben wird `True` , wird die zweite Prozedur nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ce001-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="ce001-142">Dies kann zu unerwarteten Ergebnissen führen, wenn die zweite Prozedur wichtige Aufgaben durchführt, die immer ausgeführt werden sollten, wenn dieser Code Abschnitt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce001-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="ce001-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce001-143">See also</span></span>

- [<span data-ttu-id="ce001-144">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce001-144">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="ce001-145">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce001-145">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="ce001-146">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ce001-146">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ce001-147">Or-Operator</span><span class="sxs-lookup"><span data-stu-id="ce001-147">Or Operator</span></span>](or-operator.md)
- [<span data-ttu-id="ce001-148">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="ce001-148">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="ce001-149">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce001-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
