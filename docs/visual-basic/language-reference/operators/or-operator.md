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
ms.openlocfilehash: f6cfd1073ada42aa2db8be9b14c81319bc0db294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874756"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="27695-102">Or-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27695-102">Or Operator (Visual Basic)</span></span>

<span data-ttu-id="27695-103">Führt eine logische Disjunktion zweier `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="27695-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27695-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27695-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="27695-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="27695-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="27695-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27695-106">Required.</span></span> <span data-ttu-id="27695-107">Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="27695-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="27695-108">Zum `Boolean` Vergleich `result` ist die inklusivlogische Disjunktion von zwei `Boolean` Werten.</span><span class="sxs-lookup"><span data-stu-id="27695-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="27695-109">Für bitweise Vorgänge `result` ist ein numerischer Wert, der die inklusive bitweise Disjunktion zweier numerischer Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="27695-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="27695-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27695-110">Required.</span></span> <span data-ttu-id="27695-111">Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="27695-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="27695-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27695-112">Required.</span></span> <span data-ttu-id="27695-113">Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="27695-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27695-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="27695-114">Remarks</span></span>  

 <span data-ttu-id="27695-115">Zum `Boolean` Vergleich `result` ist `False` nur dann, wenn sowohl `expression1` als `expression2` `False` auch als ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="27695-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="27695-116">In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="27695-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="27695-117">Wenn `expression1` gleich </span><span class="sxs-lookup"><span data-stu-id="27695-117">If `expression1` is</span></span>|<span data-ttu-id="27695-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="27695-118">And `expression2` is</span></span>|<span data-ttu-id="27695-119">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="27695-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="27695-120">In einem `Boolean` Vergleich wertet der- `Or` Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können.</span><span class="sxs-lookup"><span data-stu-id="27695-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="27695-121">Der [OrElse-Operator](orelse-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression1` , wenn gleich ist `True` , `expression2` nicht ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="27695-121">The [OrElse Operator](orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="27695-122">Für bitweise Operationen führt der- `Or` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken aus und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="27695-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="27695-123">Wenn `expression1` Bit in</span><span class="sxs-lookup"><span data-stu-id="27695-123">If bit in `expression1` is</span></span>|<span data-ttu-id="27695-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="27695-124">And bit in `expression2` is</span></span>|<span data-ttu-id="27695-125">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="27695-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="27695-126">1</span><span class="sxs-lookup"><span data-stu-id="27695-126">1</span></span>|<span data-ttu-id="27695-127">1</span><span class="sxs-lookup"><span data-stu-id="27695-127">1</span></span>|<span data-ttu-id="27695-128">1</span><span class="sxs-lookup"><span data-stu-id="27695-128">1</span></span>|  
|<span data-ttu-id="27695-129">1</span><span class="sxs-lookup"><span data-stu-id="27695-129">1</span></span>|<span data-ttu-id="27695-130">0</span><span class="sxs-lookup"><span data-stu-id="27695-130">0</span></span>|<span data-ttu-id="27695-131">1</span><span class="sxs-lookup"><span data-stu-id="27695-131">1</span></span>|  
|<span data-ttu-id="27695-132">0</span><span class="sxs-lookup"><span data-stu-id="27695-132">0</span></span>|<span data-ttu-id="27695-133">1</span><span class="sxs-lookup"><span data-stu-id="27695-133">1</span></span>|<span data-ttu-id="27695-134">1</span><span class="sxs-lookup"><span data-stu-id="27695-134">1</span></span>|  
|<span data-ttu-id="27695-135">0</span><span class="sxs-lookup"><span data-stu-id="27695-135">0</span></span>|<span data-ttu-id="27695-136">0</span><span class="sxs-lookup"><span data-stu-id="27695-136">0</span></span>|<span data-ttu-id="27695-137">0</span><span class="sxs-lookup"><span data-stu-id="27695-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="27695-138">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="27695-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="27695-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="27695-139">Data Types</span></span>  

 <span data-ttu-id="27695-140">Wenn die Operanden aus einem `Boolean` Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False` ) und führt eine bitweise Operation aus.</span><span class="sxs-lookup"><span data-stu-id="27695-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="27695-141">Für einen `Boolean` Vergleich ist der Datentyp des Ergebnisses `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="27695-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="27695-142">Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und geeignet ist `expression2` .</span><span class="sxs-lookup"><span data-stu-id="27695-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="27695-143">Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="27695-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="27695-144">Überladen</span><span class="sxs-lookup"><span data-stu-id="27695-144">Overloading</span></span>  

 <span data-ttu-id="27695-145">Der `Or` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="27695-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="27695-146">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="27695-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="27695-147">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="27695-147">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27695-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27695-148">Example</span></span>  

 <span data-ttu-id="27695-149">Im folgenden Beispiel wird der- `Or` Operator verwendet, um eine inklusivlogische Disjunktion für zwei Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="27695-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="27695-150">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob einer der beiden Ausdrücke ist `True` .</span><span class="sxs-lookup"><span data-stu-id="27695-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="27695-151">Im vorherigen Beispiel werden die Ergebnisse von `True` , `True` `False` bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="27695-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27695-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27695-152">Example</span></span>  

 <span data-ttu-id="27695-153">Im folgenden Beispiel wird der- `Or` Operator verwendet, um die inklusive logische Disjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen.</span><span class="sxs-lookup"><span data-stu-id="27695-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="27695-154">Das Bit im Ergebnis Muster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="27695-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="27695-155">Das vorherige Beispiel erzeugt die Ergebnisse von 10, 14 und 14.</span><span class="sxs-lookup"><span data-stu-id="27695-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27695-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27695-156">See also</span></span>

- [<span data-ttu-id="27695-157">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27695-157">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="27695-158">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27695-158">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="27695-159">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="27695-159">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="27695-160">OrElse-Operator</span><span class="sxs-lookup"><span data-stu-id="27695-160">OrElse Operator</span></span>](orelse-operator.md)
- [<span data-ttu-id="27695-161">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27695-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
