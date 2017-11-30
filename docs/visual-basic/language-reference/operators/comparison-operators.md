---
title: Vergleichsoperatoren (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="ce399-102">Vergleichsoperatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce399-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="ce399-103">Es folgen die Vergleichsoperatoren in Visual Basic definiert.</span><span class="sxs-lookup"><span data-stu-id="ce399-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="ce399-104">`<`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-104">`<` operator</span></span>  
  
 <span data-ttu-id="ce399-105">`<=`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-105">`<=` operator</span></span>  
  
 <span data-ttu-id="ce399-106">`>`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-106">`>` operator</span></span>  
  
 <span data-ttu-id="ce399-107">`>=`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-107">`>=` operator</span></span>  
  
 <span data-ttu-id="ce399-108">`=`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-108">`=` operator</span></span>  
  
 <span data-ttu-id="ce399-109">`<>`Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="ce399-110">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="ce399-111">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="ce399-112">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="ce399-113">Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob sie gleich sind, und falls nicht, wie sie unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ce399-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="ce399-114">`Is`, `IsNot`, und `Like` werden auf separaten Hilfeseiten im Detail besprochen.</span><span class="sxs-lookup"><span data-stu-id="ce399-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="ce399-115">Die relationalen Vergleichsoperatoren werden auf dieser Seite im Detail erläutert.</span><span class="sxs-lookup"><span data-stu-id="ce399-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce399-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce399-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="ce399-117">Teile</span><span class="sxs-lookup"><span data-stu-id="ce399-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="ce399-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-118">Required.</span></span> <span data-ttu-id="ce399-119">Ein `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="ce399-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="ce399-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-120">Required.</span></span> <span data-ttu-id="ce399-121">Beliebiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce399-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="ce399-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-122">Required.</span></span> <span data-ttu-id="ce399-123">Alle relationalen Vergleichsoperator.</span><span class="sxs-lookup"><span data-stu-id="ce399-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="ce399-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="ce399-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="ce399-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-125">Required.</span></span> <span data-ttu-id="ce399-126">Jeder Verweis zu verwendenden Objektnamen.</span><span class="sxs-lookup"><span data-stu-id="ce399-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="ce399-127">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-127">Required.</span></span> <span data-ttu-id="ce399-128">Beliebiger `String`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ce399-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="ce399-129">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce399-129">Required.</span></span> <span data-ttu-id="ce399-130">Alle `String` Ausdruck oder einen Bereich von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ce399-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce399-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce399-131">Remarks</span></span>  
 <span data-ttu-id="ce399-132">Die folgende Tabelle enthält eine Liste von Vergleichsoperatoren für den relationalen und die Bedingungen, die bestimmen, ob `result` ist `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="ce399-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="ce399-133">Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-133">Operator</span></span>|<span data-ttu-id="ce399-134">`True`if</span><span class="sxs-lookup"><span data-stu-id="ce399-134">`True` if</span></span>|<span data-ttu-id="ce399-135">`False`if</span><span class="sxs-lookup"><span data-stu-id="ce399-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="ce399-136">`<`(Kleiner als)</span><span class="sxs-lookup"><span data-stu-id="ce399-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="ce399-137">`<=`(Kleiner als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="ce399-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="ce399-138">`>`(Größer als)</span><span class="sxs-lookup"><span data-stu-id="ce399-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="ce399-139">`>=`(Größer als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="ce399-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="ce399-140">`=`(Gleich)</span><span class="sxs-lookup"><span data-stu-id="ce399-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="ce399-141">`<>`(Ungleich)</span><span class="sxs-lookup"><span data-stu-id="ce399-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="ce399-142">Die [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungsoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce399-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="ce399-143">Die `Is` -Operator, der `IsNot` -Operator, und die `Like` Operator haben spezifische Vergleich-Funktionen, die von den Operatoren in der obigen Tabelle unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ce399-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="ce399-144">Vergleichen von Zahlen</span><span class="sxs-lookup"><span data-stu-id="ce399-144">Comparing Numbers</span></span>  
 <span data-ttu-id="ce399-145">Wenn Sie einen Ausdruck vom Typ vergleichen `Single` auf einen Typ `Double`, die `Single` Ausdruck konvertiert `Double`.</span><span class="sxs-lookup"><span data-stu-id="ce399-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="ce399-146">Dieses Verhalten ist Gegensatz zum Verhalten in Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="ce399-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="ce399-147">Auf ähnliche Weise, wenn Sie einen Ausdruck vom Typ vergleichen `Decimal` auf einen Ausdruck vom Typ `Single` oder `Double`, `Decimal` Ausdruck konvertiert `Single` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="ce399-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="ce399-148">Für `Decimal` Ausdrücke, alle Dezimalstellenwert kleiner als 1E-28 möglicherweise verloren.</span><span class="sxs-lookup"><span data-stu-id="ce399-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="ce399-149">Datenverluste Dezimalstellenwert kann bewirken, dass zwei Werte als gleich verglichen werden soll, wenn sie nicht sind.</span><span class="sxs-lookup"><span data-stu-id="ce399-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="ce399-150">Aus diesem Grund sollten Sie darauf achten bei Verwendung von Gleichheit (`=`), zwei Gleitkommavariablen verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce399-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="ce399-151">Es ist sicherer, testen, ob der Absolute Wert des Unterschieds zwischen zwei Zahlen, die kleiner als eine kleine akzeptable Toleranz ist.</span><span class="sxs-lookup"><span data-stu-id="ce399-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="ce399-152">Gleitkomma Ungenauigkeit</span><span class="sxs-lookup"><span data-stu-id="ce399-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="ce399-153">Beim Arbeiten mit Gleitkommazahlen, sollten Sie bedenken, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce399-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="ce399-154">Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ce399-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="ce399-155">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ce399-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="ce399-156">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ce399-156">Comparing Strings</span></span>  
 <span data-ttu-id="ce399-157">Wenn Sie Zeichenfolgen vergleichen, die Zeichenfolgenausdrücke werden ausgewertet basierend auf deren Reihenfolge alphabetisch sortiert, abhängig von der `Option Compare` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ce399-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="ce399-158">`Option Compare Binary`Führt einen Zeichenfolgenvergleich auf einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ce399-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="ce399-159">Die Sortierreihenfolge wird durch die Codepage bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ce399-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="ce399-160">Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="ce399-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="ce399-161">`Option Compare Text`Führt einen Zeichenfolgenvergleich durch Ihre Anwendung Gebietsschema bestimmt Groß-/Kleinschreibung, Text Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ce399-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="ce399-162">Bei Festlegung `Option Compare Text` und die Zeichen im vorangehenden Beispiel sortieren, gilt die folgende Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="ce399-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="ce399-163">Abhängigkeit vom Gebietsschema</span><span class="sxs-lookup"><span data-stu-id="ce399-163">Locale Dependence</span></span>  
 <span data-ttu-id="ce399-164">Bei Festlegung `Option Compare Text`, kann das Ergebnis eines Zeichenfolgenvergleichs abhängen, auf dem Gebietsschema, in dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce399-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="ce399-165">Zwei Zeichen möglicherweise als gleichwertig in einem Gebietsschema aber nicht in einer anderen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ce399-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="ce399-166">Wenn Sie einen Zeichenfolgenvergleich verwenden werden, um einige wichtige Entscheidungen, z. B. ob ein Anmeldeversuch, akzeptieren sollten Sie die Warnung, um Gebietsschema Empfindlichkeit sein.</span><span class="sxs-lookup"><span data-stu-id="ce399-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="ce399-167">Legen Sie entweder `Option Compare Binary` oder aufrufende der <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, die berücksichtigt des Gebietsschemas.</span><span class="sxs-lookup"><span data-stu-id="ce399-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="ce399-168">Programmierung ohne Datentypen mit relationalen Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ce399-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="ce399-169">Die Verwendung von relationalen Vergleichsoperatoren mit `Object` Ausdrücke darf nicht unter `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="ce399-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="ce399-170">Wenn `Option Strict` ist `Off`, und entweder `expression1` oder `expression2` ist ein `Object` Ausdruck, der Typen zur Laufzeit zu bestimmen, wie sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="ce399-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="ce399-171">Die folgende Tabelle zeigt, wie die Ausdrücke verglichen werden und das Ergebnis des Vergleichs, abhängig von der Common Language Runtime-Typ der Operanden.</span><span class="sxs-lookup"><span data-stu-id="ce399-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="ce399-172">Wenn die Operanden sind</span><span class="sxs-lookup"><span data-stu-id="ce399-172">If operands are</span></span>|<span data-ttu-id="ce399-173">Vergleich</span><span class="sxs-lookup"><span data-stu-id="ce399-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="ce399-174">Beide`String`</span><span class="sxs-lookup"><span data-stu-id="ce399-174">Both `String`</span></span>|<span data-ttu-id="ce399-175">Vergleich basierend auf Eigenschaften zum Sortieren von Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ce399-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="ce399-176">Beide numerisch</span><span class="sxs-lookup"><span data-stu-id="ce399-176">Both numeric</span></span>|<span data-ttu-id="ce399-177">Objekte in konvertiert `Double`, numerischen Vergleich.</span><span class="sxs-lookup"><span data-stu-id="ce399-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="ce399-178">Eine numerische und eine`String`</span><span class="sxs-lookup"><span data-stu-id="ce399-178">One numeric and one `String`</span></span>|<span data-ttu-id="ce399-179">Die `String` konvertiert eine `Double` und numerischen Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ce399-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="ce399-180">Wenn die `String` kann nicht konvertiert werden, um `Double`, wird eine <xref:System.InvalidCastException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ce399-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="ce399-181">Eine oder beide sind Referenztypen außer`String`</span><span class="sxs-lookup"><span data-stu-id="ce399-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="ce399-182">Es wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ce399-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="ce399-183">Behandeln von numerische vergleichen `Nothing` als 0.</span><span class="sxs-lookup"><span data-stu-id="ce399-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="ce399-184">Behandeln von Zeichenfolgenvergleichen `Nothing` als `""` (eine leere Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="ce399-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ce399-185">Überladen</span><span class="sxs-lookup"><span data-stu-id="ce399-185">Overloading</span></span>  
 <span data-ttu-id="ce399-186">Die relationalen Vergleichsoperatoren (`<`.</span><span class="sxs-lookup"><span data-stu-id="ce399-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="ce399-187">`<=``>`, `>=`, `=`, `<>`) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur ihr Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="ce399-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ce399-188">Wenn Ihr Code einen dieser Operatoren auf solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="ce399-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="ce399-189">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ce399-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="ce399-190">Beachten Sie, dass die [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationalen Vergleichsoperator und nicht als Zuweisungsoperator überladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ce399-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce399-191">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce399-191">Example</span></span>  
 <span data-ttu-id="ce399-192">Das folgende Beispiel zeigt verschiedene Verwendungsmöglichkeiten der relationalen Vergleichsoperatoren, die Sie zum Vergleichen von Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce399-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="ce399-193">Relationale Vergleichsoperatoren Zurückgeben einer `Boolean` Ergebnis, das darstellt, und zwar unabhängig davon, ob der angegebene Ausdruck ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="ce399-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="ce399-194">Beim Anwenden der `>` und `<` Operatoren in Zeichenfolgen, der Vergleich erfolgt mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="ce399-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="ce399-195">Diese Reihenfolge kann Ihr Gebietsschema abhängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ce399-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="ce399-196">Gibt an, ob die Sortierung Groß-/Kleinschreibung beachtet wird, hängt die [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ce399-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="ce399-197">Im vorherigen Beispiel gibt der erste Vergleich `False` und die verbleibenden Vergleiche zurückgeben `True`.</span><span class="sxs-lookup"><span data-stu-id="ce399-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce399-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce399-198">See Also</span></span>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="ce399-199">=-Operator</span><span class="sxs-lookup"><span data-stu-id="ce399-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="ce399-200">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce399-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ce399-201">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ce399-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ce399-202">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="ce399-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="ce399-203">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce399-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
