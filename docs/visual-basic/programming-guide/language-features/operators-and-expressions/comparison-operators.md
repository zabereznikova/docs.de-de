---
title: Vergleichsoperatoren in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- comparison operators, comparing strings
- comparison operators, comparing objects
- strings [Visual Basic], comparing
- comparison operators
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers, comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values, comparing
- comparison operators, comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a958481fa04cb1a9abde69c5215dccd6dbbe4a14
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="bfd5f-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfd5f-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="bfd5f-103">Vergleichsoperatoren vergleichen zwei Ausdrücke und geben einen `Boolean` Wert, der die Beziehung zwischen ihren Werten darstellt.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="bfd5f-104">Es gibt Operatoren für das Vergleichen von numerischen Werten, Operatoren für Zeichenfolgen und Operatoren zum Vergleichen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="bfd5f-105">Alle drei Typen von Operatoren werden in diesem Dokument erläutert.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="bfd5f-106">Vergleichen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="bfd5f-106">Comparing Numeric Values</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="bfd5f-107">Vergleicht numerische Werte mithilfe von sechs numerischen Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-107"> compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="bfd5f-108">Jeder Operator akzeptiert zwei Ausdrücke, die numerische Werte ergeben, als Operanden.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="bfd5f-109">In der folgenden Tabelle werden die Operatoren aufgelistet und zeigt Beispiele für jeden.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="bfd5f-110">Operator</span><span class="sxs-lookup"><span data-stu-id="bfd5f-110">Operator</span></span>|<span data-ttu-id="bfd5f-111">Getestete Bedingung</span><span class="sxs-lookup"><span data-stu-id="bfd5f-111">Condition tested</span></span>|<span data-ttu-id="bfd5f-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bfd5f-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="bfd5f-113">`=`(Gleichheit)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-113">`=` (Equality)</span></span>|<span data-ttu-id="bfd5f-114">Ist der Wert des ersten Ausdrucks gleich dem Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="bfd5f-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="bfd5f-118">`<>`(Ungleichheit)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-118">`<>` (Inequality)</span></span>|<span data-ttu-id="bfd5f-119">Ist der Wert des ersten Ausdrucks ungleich dem Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="bfd5f-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="bfd5f-123">`<`(Kleiner als)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-123">`<` (Less than)</span></span>|<span data-ttu-id="bfd5f-124">Ist der Wert des ersten Ausdrucks kleiner als der Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="bfd5f-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="bfd5f-128">`>`(Größer als)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-128">`>` (Greater than)</span></span>|<span data-ttu-id="bfd5f-129">Ist der Wert des ersten Ausdrucks größer als der Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="bfd5f-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="bfd5f-133">`<=`(Kleiner als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="bfd5f-134">Ist der Wert des ersten Ausdrucks kleiner oder gleich dem Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="bfd5f-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="bfd5f-138">`>=`(Größer als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="bfd5f-139">Ist der Wert des ersten Ausdrucks, größer als oder gleich dem Wert des zweiten?</span><span class="sxs-lookup"><span data-stu-id="bfd5f-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="bfd5f-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="bfd5f-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="bfd5f-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="bfd5f-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="bfd5f-143">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="bfd5f-143">Comparing Strings</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="bfd5f-144">vergleicht Zeichenfolgen anhand der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md) sowie den numerischen Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-144"> compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="bfd5f-145">Die `Like` Operator können Sie ein Muster angeben.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="bfd5f-146">Die Zeichenfolge wird dann mit dem Muster verglichen, und bei Übereinstimmung ist das Ergebnis ist `True`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="bfd5f-147">Andernfalls das Ergebnis ist `False`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="bfd5f-148">Mit den numerischen Operatoren können Sie vergleichen `String` Werte basierend auf ihrer Sortierreihenfolge wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="bfd5f-149">Das Ergebnis im vorherigen Beispiel ist `True` , da das erste Zeichen in der ersten Zeichenfolge vor dem ersten Zeichen in der zweiten Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="bfd5f-150">Wenn die ersten Zeichen gleich wären, würde der Vergleich weiterhin auf das nächste Zeichen in beiden Zeichenfolgen usw..</span><span class="sxs-lookup"><span data-stu-id="bfd5f-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="bfd5f-151">Sie können auch mit dem Gleichheitsoperator, wie im folgenden Beispiel gezeigt Zeichenfolgen auf Gleichheit testen.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="bfd5f-152">Wenn eine Zeichenfolge einer anderen vorangestellt, z. B. "aa" und "aaa", gilt die längere Zeichenfolge größer als die kürzere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="bfd5f-153">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="bfd5f-154">Die Sortierreihenfolge basiert auf einem binären Vergleich oder einen Textvergleich abhängig von der Einstellung des `Option Compare`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="bfd5f-155">Weitere Informationen finden Sie unter [Option Compare-Anweisung](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bfd5f-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="bfd5f-156">Vergleichen von Objekten</span><span class="sxs-lookup"><span data-stu-id="bfd5f-156">Comparing Objects</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="bfd5f-157">Vergleicht zwei Objektverweisvariablen mit dem [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) und [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bfd5f-157"> compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="bfd5f-158">Sie können beiden Operatoren verwenden, um festzustellen, ob zwei Verweisvariablen auf die gleiche Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="bfd5f-159">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-159">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="bfd5f-160">[!code-vb[VbVbalrOperators&#65;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfd5f-160">[!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="bfd5f-161">Im vorangehenden Beispiel `x Is y` ergibt `True`, da beide Variablen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-161">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="bfd5f-162">Vergleichen Sie dieses Ergebnis mit dem folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-162">Contrast this result with the following example.</span></span>  
  
 <span data-ttu-id="bfd5f-163">[!code-vb[VbVbalrOperators&#66;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfd5f-163">[!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="bfd5f-164">Im vorangehenden Beispiel `x Is y` ergibt `False`, da die Variablen zwar auf Objekte vom gleichen Typ, jedoch auf unterschiedliche Instanzen dieses Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-164">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="bfd5f-165">Wenn Sie zwei Objekte nicht auf dieselbe Instanz verweisen möchten die `IsNot` Operator können Sie eine umständliche Grammatik einer Kombination von vermeiden `Not` und `Is`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-165">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="bfd5f-166">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-166">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="bfd5f-167">[!code-vb[VbVbalrOperators&#67;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfd5f-167">[!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span></span>  
  
 <span data-ttu-id="bfd5f-168">Im vorangehenden Beispiel `If a IsNot b` entspricht `If Not a Is b`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-168">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="bfd5f-169">Vergleichen des Objekttyps</span><span class="sxs-lookup"><span data-stu-id="bfd5f-169">Comparing Object Type</span></span>  
 <span data-ttu-id="bfd5f-170">Sie können testen, ob ein Objekt eines bestimmten Typs mit der `TypeOf`... `Is` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-170">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="bfd5f-171">Die Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bfd5f-171">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="bfd5f-172">Wenn `typename` gibt einen Schnittstellentyp, der `TypeOf`... `Is` gibt `True` , wenn das Objekt den Schnittstellentyp implementiert.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-172">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="bfd5f-173">Wenn `typename` ein Klassentyp ist, gibt der Ausdruck `True` Wenn das Objekt eine Instanz der angegebenen Klasse oder eine Klasse, die von der angegebenen Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-173">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="bfd5f-174">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-174">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="bfd5f-175">[!code-vb[VbVbalrOperators&#68;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfd5f-175">[!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span></span>  
  
 <span data-ttu-id="bfd5f-176">Im vorhergehenden Beispiel die `TypeOf x Is Control` Ausdruck ergibt `True` da der Typ des `x` ist `Button`, erbt von `Control`.</span><span class="sxs-lookup"><span data-stu-id="bfd5f-176">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="bfd5f-177">Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bfd5f-177">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd5f-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd5f-178">See Also</span></span>  
 <span data-ttu-id="bfd5f-179">[Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="bfd5f-179">[Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="bfd5f-180"> [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bfd5f-180"> [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="bfd5f-181"> [Operatoren](../../../../visual-basic/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="bfd5f-181"> [Operators](../../../../visual-basic/language-reference/operators/index.md) </span></span>  
<span data-ttu-id="bfd5f-182"> [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bfd5f-182"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="bfd5f-183"> [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bfd5f-183"> [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span></span>  
<span data-ttu-id="bfd5f-184"> [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="bfd5f-184"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
