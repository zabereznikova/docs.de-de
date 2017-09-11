---
title: OR -Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Or
dev_langs:
- VB
helpviewer_keywords:
- Or operator
- operators [Visual Basic], bitwise
- inclusive Or operator
- bitwise operators, OR operator
- Or keyword
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison
- logical disjunction
- disjunction operator
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 01d51f50dd785f168ed850e3f1763b300d9d2011
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="8b8a0-102">Or-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b8a0-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="8b8a0-103">Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion für zwei numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b8a0-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8b8a0-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8b8a0-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8b8a0-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-106">Required.</span></span> <span data-ttu-id="8b8a0-107">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="8b8a0-108">Für `Boolean` Vergleich `result` ist die inklusive logische Disjunktion zweier `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="8b8a0-109">Bei bitweisen Operationen `result` einen numerischen Wert, der die inklusive bitweise Disjunktion von zwei numerischen Bitmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8b8a0-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-110">Required.</span></span> <span data-ttu-id="8b8a0-111">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8b8a0-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-112">Required.</span></span> <span data-ttu-id="8b8a0-113">Alle `Boolean` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b8a0-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b8a0-114">Remarks</span></span>  
 <span data-ttu-id="8b8a0-115">Für `Boolean` Vergleich `result` ist `False` Wenn und nur wenn beide `expression1` und `expression2` ergeben `False`.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="8b8a0-116">Die folgende Tabelle verdeutlicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8b8a0-117">If `expression1` is</span><span class="sxs-lookup"><span data-stu-id="8b8a0-117">If `expression1` is</span></span>|<span data-ttu-id="8b8a0-118">Und `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="8b8a0-118">And `expression2` is</span></span>|<span data-ttu-id="8b8a0-119">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="8b8a0-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="8b8a0-120">In einem `Boolean` Vergleich der `Or` Operator ergibt immer beide Ausdrücke aus, wobei u. u. Prozeduraufrufe.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="8b8a0-121">Die [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *eine verkürzte*, was bedeutet, dass bei `expression1` ist `True`, dann `expression2` wird nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="8b8a0-122">Bei bitweisen Operationen der `Or` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit im `result` gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8b8a0-123">Wenn bit im `expression1` ist</span><span class="sxs-lookup"><span data-stu-id="8b8a0-123">If bit in `expression1` is</span></span>|<span data-ttu-id="8b8a0-124">Und Bit in `expression2` ist</span><span class="sxs-lookup"><span data-stu-id="8b8a0-124">And bit in `expression2` is</span></span>|<span data-ttu-id="8b8a0-125">Das Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="8b8a0-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="8b8a0-126">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-126">1</span></span>|<span data-ttu-id="8b8a0-127">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-127">1</span></span>|<span data-ttu-id="8b8a0-128">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-128">1</span></span>|  
|<span data-ttu-id="8b8a0-129">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-129">1</span></span>|<span data-ttu-id="8b8a0-130">0</span><span class="sxs-lookup"><span data-stu-id="8b8a0-130">0</span></span>|<span data-ttu-id="8b8a0-131">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-131">1</span></span>|  
|<span data-ttu-id="8b8a0-132">0</span><span class="sxs-lookup"><span data-stu-id="8b8a0-132">0</span></span>|<span data-ttu-id="8b8a0-133">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-133">1</span></span>|<span data-ttu-id="8b8a0-134">1</span><span class="sxs-lookup"><span data-stu-id="8b8a0-134">1</span></span>|  
|<span data-ttu-id="8b8a0-135">0</span><span class="sxs-lookup"><span data-stu-id="8b8a0-135">0</span></span>|<span data-ttu-id="8b8a0-136">0</span><span class="sxs-lookup"><span data-stu-id="8b8a0-136">0</span></span>|<span data-ttu-id="8b8a0-137">0</span><span class="sxs-lookup"><span data-stu-id="8b8a0-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8b8a0-138">Da die logischen und bitweisen Operatoren einen niedrigeren Rang als andere arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um genaue Ausführung gewährleistet eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8b8a0-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8b8a0-139">Data Types</span></span>  
 <span data-ttu-id="8b8a0-140">Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="8b8a0-141">Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8b8a0-142">Einen bitweisen Vergleich ist der resultierende Datentyp eines numerischen Typs für die Datentypen der `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="8b8a0-143">Siehe die Tabelle "Relationale und bitweise Vergleiche" in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b8a0-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8b8a0-144">Überladen</span><span class="sxs-lookup"><span data-stu-id="8b8a0-144">Overloading</span></span>  
 <span data-ttu-id="8b8a0-145">Die `Or` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8b8a0-146">Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8b8a0-147">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8b8a0-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8a0-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b8a0-148">Example</span></span>  
 <span data-ttu-id="8b8a0-149">Im folgenden Beispiel wird die `Or` Operator, um eine inklusive logische Disjunktion zweier Ausdrücke ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="8b8a0-150">Das Ergebnis ist ein `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke `True`.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 <span data-ttu-id="8b8a0-151">[!code-vb[VbVbalrOperators&#35;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b8a0-151">[!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="8b8a0-152">Im vorherigen Beispiel ergibt der `True`, `True`, und `False`bzw..</span><span class="sxs-lookup"><span data-stu-id="8b8a0-152">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8a0-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b8a0-153">Example</span></span>  
 <span data-ttu-id="8b8a0-154">Im folgenden Beispiel wird die `Or` Operator inklusiven logische Disjunktion der einzelnen Bits von zwei numerischen Ausdrücken ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-154">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="8b8a0-155">Das Bit im Ergebnismuster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-155">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 <span data-ttu-id="8b8a0-156">[!code-vb[VbVbalrOperators Nr.&36;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b8a0-156">[!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span></span>  
  
 <span data-ttu-id="8b8a0-157">Im vorherigen Beispiel werden die Ergebnisse 10, 14 und 14 bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="8b8a0-157">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8a0-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b8a0-158">See Also</span></span>  
 <span data-ttu-id="8b8a0-159">[Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span><span class="sxs-lookup"><span data-stu-id="8b8a0-159">[Logical/Bitwise Operators (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span></span>  
<span data-ttu-id="8b8a0-160"> [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="8b8a0-160"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="8b8a0-161"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="8b8a0-161"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="8b8a0-162"> [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8b8a0-162"> [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) </span></span>  
<span data-ttu-id="8b8a0-163"> [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="8b8a0-163"> [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>

