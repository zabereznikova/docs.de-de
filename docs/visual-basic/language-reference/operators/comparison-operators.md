---
title: Vergleichsoperatoren
ms.date: 07/20/2015
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
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: bcd51d70c5c7bd08991c7433e244316a82daa9da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371790"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="fc435-102">Vergleichsoperatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc435-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="fc435-103">Im folgenden sind die in Visual Basic definierten Vergleichs Operatoren angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc435-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="fc435-104">`<`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-104">`<` operator</span></span>

 <span data-ttu-id="fc435-105">`<=`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-105">`<=` operator</span></span>

 <span data-ttu-id="fc435-106">`>`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-106">`>` operator</span></span>

 <span data-ttu-id="fc435-107">`>=`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-107">`>=` operator</span></span>

 <span data-ttu-id="fc435-108">`=`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-108">`=` operator</span></span>

 <span data-ttu-id="fc435-109">`<>`KOM</span><span class="sxs-lookup"><span data-stu-id="fc435-109">`<>` operator</span></span>

 [<span data-ttu-id="fc435-110">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="fc435-110">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="fc435-111">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="fc435-111">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="fc435-112">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="fc435-112">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="fc435-113">Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob Sie gleich sind, und falls nicht, wie Sie sich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fc435-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="fc435-114">`Is`, `IsNot` und `Like` werden auf separaten Hilfeseiten ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="fc435-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="fc435-115">Die relationalen Vergleichs Operatoren werden auf dieser Seite ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="fc435-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc435-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc435-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="fc435-117">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="fc435-117">Parts</span></span>
 `result`  
 <span data-ttu-id="fc435-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-118">Required.</span></span> <span data-ttu-id="fc435-119">Ein- `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc435-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="fc435-120">`expression1`, `expression2`</span><span class="sxs-lookup"><span data-stu-id="fc435-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="fc435-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-121">Required.</span></span> <span data-ttu-id="fc435-122">Beliebiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fc435-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="fc435-123">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-123">Required.</span></span> <span data-ttu-id="fc435-124">Ein beliebiger relationaler Vergleichs Operator.</span><span class="sxs-lookup"><span data-stu-id="fc435-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="fc435-125">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="fc435-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="fc435-126">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-126">Required.</span></span> <span data-ttu-id="fc435-127">Alle Verweis Objektnamen.</span><span class="sxs-lookup"><span data-stu-id="fc435-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="fc435-128">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-128">Required.</span></span> <span data-ttu-id="fc435-129">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fc435-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="fc435-130">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc435-130">Required.</span></span> <span data-ttu-id="fc435-131">Beliebiger `String` Ausdruck oder Zeichenbereich.</span><span class="sxs-lookup"><span data-stu-id="fc435-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc435-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc435-132">Remarks</span></span>
 <span data-ttu-id="fc435-133">Die folgende Tabelle enthält eine Liste der relationalen Vergleichs Operatoren und die Bedingungen, die bestimmen, ob `result` `True` oder ist `False` .</span><span class="sxs-lookup"><span data-stu-id="fc435-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="fc435-134">Operator</span><span class="sxs-lookup"><span data-stu-id="fc435-134">Operator</span></span>|<span data-ttu-id="fc435-135">`True`, wenn</span><span class="sxs-lookup"><span data-stu-id="fc435-135">`True` if</span></span>|<span data-ttu-id="fc435-136">`False`, wenn</span><span class="sxs-lookup"><span data-stu-id="fc435-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="fc435-137">`<`(Kleiner als)</span><span class="sxs-lookup"><span data-stu-id="fc435-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="fc435-138">`<=`(Kleiner als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="fc435-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="fc435-139">`>`(Größer als)</span><span class="sxs-lookup"><span data-stu-id="fc435-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="fc435-140">`>=`(Größer als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="fc435-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="fc435-141">`=`(Gleich)</span><span class="sxs-lookup"><span data-stu-id="fc435-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="fc435-142">`<>`(Ungleich)</span><span class="sxs-lookup"><span data-stu-id="fc435-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="fc435-143">Der [Operator =](assignment-operator.md) wird auch als Zuweisungs Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc435-143">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="fc435-144">Der `Is` -Operator, der `IsNot` -Operator und der- `Like` Operator verfügen über bestimmte Vergleichs Funktionalitäten, die sich von den Operatoren in der obigen Tabelle unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="fc435-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="fc435-145">Vergleichen von Zahlen</span><span class="sxs-lookup"><span data-stu-id="fc435-145">Comparing Numbers</span></span>
 <span data-ttu-id="fc435-146">Wenn Sie einen Ausdruck vom Typ `Single` mit einem vom Typ vergleichen `Double` , `Single` wird der Ausdruck in konvertiert `Double` .</span><span class="sxs-lookup"><span data-stu-id="fc435-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="fc435-147">Dieses Verhalten steht im Gegensatz zu dem in Visual Basic 6 gefundenen Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fc435-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="fc435-148">Wenn Sie einen Ausdruck vom Typ `Decimal` mit einem Ausdruck vom Typ `Single` oder vergleichen `Double` , `Decimal` wird der Ausdruck ebenso in oder konvertiert `Single` `Double` .</span><span class="sxs-lookup"><span data-stu-id="fc435-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="fc435-149">Bei `Decimal` Ausdrücken können alle Bruchzahlen, die kleiner als 1E-28 sind, verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="fc435-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="fc435-150">Ein solcher Verlust von Bruchteil-Werten kann bewirken, dass zwei Werte als gleich verglichen werden, wenn Sie nicht sind.</span><span class="sxs-lookup"><span data-stu-id="fc435-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="fc435-151">Aus diesem Grund sollten Sie bei der Verwendung von Gleichheit () darauf achten, `=` zwei Gleit Komma Variablen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="fc435-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="fc435-152">Es ist sicherer, zu testen, ob der absolute Wert des Unterschieds zwischen den beiden Zahlen kleiner als eine geringfügige akzeptable Toleranz ist.</span><span class="sxs-lookup"><span data-stu-id="fc435-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="fc435-153">Ungenauigkeit von Gleit Komma Werten</span><span class="sxs-lookup"><span data-stu-id="fc435-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="fc435-154">Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="fc435-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="fc435-155">Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der [Mod-Operator](mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fc435-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="fc435-156">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc435-156">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="fc435-157">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fc435-157">Comparing Strings</span></span>
 <span data-ttu-id="fc435-158">Beim Vergleichen von Zeichen folgen werden die Zeichen folgen Ausdrücke basierend auf der alphabetischen Sortierreihenfolge ausgewertet, die von der-Einstellung abhängig ist `Option Compare` .</span><span class="sxs-lookup"><span data-stu-id="fc435-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="fc435-159">`Option Compare Binary`basiert Zeichen folgen Vergleiche in einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="fc435-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="fc435-160">Die Sortierreihenfolge wird von der Codepage bestimmt.</span><span class="sxs-lookup"><span data-stu-id="fc435-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="fc435-161">Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fc435-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="fc435-162">`Option Compare Text`Basis Zeichenfolgenvergleiche bei einer Text Sortierreihenfolge ohne Beachtung der Groß-/Kleinschreibung, die durch das Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="fc435-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="fc435-163">Wenn Sie `Option Compare Text` die Zeichen im vorherigen Beispiel festlegen und sortieren, gilt die folgende Text Sortierreihenfolge:</span><span class="sxs-lookup"><span data-stu-id="fc435-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="fc435-164">Gebiets Schema Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="fc435-164">Locale Dependence</span></span>
 <span data-ttu-id="fc435-165">Wenn Sie festlegen `Option Compare Text` , kann das Ergebnis eines Zeichen folgen Vergleichs von dem Gebiets Schema abhängen, in dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fc435-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="fc435-166">Zwei Zeichen können in einem Gebiets Schema gleich sein, aber nicht in einem anderen.</span><span class="sxs-lookup"><span data-stu-id="fc435-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="fc435-167">Wenn Sie einen Zeichen folgen Vergleich verwenden, um wichtige Entscheidungen zu treffen, z. b., ob ein Anmeldeversuch angenommen werden soll, sollten Sie eine Warnung bezüglich Gebiets Schema Sensitivität haben.</span><span class="sxs-lookup"><span data-stu-id="fc435-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="fc435-168">Sie können entweder festlegen `Option Compare Binary` oder aufrufen <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , bei dem das Gebiets Schema berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc435-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="fc435-169">Typlose Programmierung mit relationalen Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="fc435-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="fc435-170">Die Verwendung von relationalen Vergleichs Operatoren mit `Object` Ausdrücken ist unter nicht zulässig `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="fc435-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="fc435-171">Wenn `Option Strict` ist `Off` und entweder `expression1` oder `expression2` ein Ausdruck ist `Object` , bestimmen die Lauf Zeit Typen, wie Sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="fc435-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="fc435-172">Die folgende Tabelle zeigt, wie die Ausdrücke und das Ergebnis des Vergleichs verglichen werden, abhängig vom Lauf Zeittyp der Operanden.</span><span class="sxs-lookup"><span data-stu-id="fc435-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="fc435-173">Wenn Operanden</span><span class="sxs-lookup"><span data-stu-id="fc435-173">If operands are</span></span>|<span data-ttu-id="fc435-174">Vergleich ist</span><span class="sxs-lookup"><span data-stu-id="fc435-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="fc435-175">Zwar`String`</span><span class="sxs-lookup"><span data-stu-id="fc435-175">Both `String`</span></span>|<span data-ttu-id="fc435-176">Sortier Vergleich auf Grundlage von Zeichen folgen Sortier Merkmalen.</span><span class="sxs-lookup"><span data-stu-id="fc435-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="fc435-177">Beide numerisch</span><span class="sxs-lookup"><span data-stu-id="fc435-177">Both numeric</span></span>|<span data-ttu-id="fc435-178">Objekte, die in konvertiert `Double` werden, numerische Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="fc435-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="fc435-179">Eine numerische und eine`String`</span><span class="sxs-lookup"><span data-stu-id="fc435-179">One numeric and one `String`</span></span>|<span data-ttu-id="fc435-180">`String`Wird in einen-Wert konvertiert, `Double` und es wird ein numerischer Vergleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc435-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="fc435-181">Wenn `String` nicht in konvertiert werden kann `Double` , wird eine ausgelöst <xref:System.InvalidCastException> .</span><span class="sxs-lookup"><span data-stu-id="fc435-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="fc435-182">Entweder oder beide sind Verweis Typen, die nicht sind.`String`</span><span class="sxs-lookup"><span data-stu-id="fc435-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="fc435-183">Es wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fc435-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="fc435-184">Numerische Vergleiche werden als 0 (null) behandelt `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="fc435-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="fc435-185">Zeichen folgen Vergleiche behandeln `Nothing` als `""` (eine leere Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="fc435-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="fc435-186">Überladen</span><span class="sxs-lookup"><span data-stu-id="fc435-186">Overloading</span></span>
 <span data-ttu-id="fc435-187">Die relationalen Vergleichs Operatoren ( `<` .</span><span class="sxs-lookup"><span data-stu-id="fc435-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="fc435-188">`<=`, `>` , `>=` , `=` , `<>` ) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="fc435-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fc435-189">Wenn Ihr Code einen dieser Operatoren in einer solchen Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="fc435-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="fc435-190">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fc435-190">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="fc435-191">Beachten Sie, dass der [=-Operator](assignment-operator.md) nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc435-191">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="fc435-192">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc435-192">Example</span></span>
 <span data-ttu-id="fc435-193">Das folgende Beispiel zeigt verschiedene Verwendungen relationaler Vergleichs Operatoren, die Sie zum Vergleichen von Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc435-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="fc435-194">Relationale Vergleichs Operatoren geben ein `Boolean` Ergebnis zurück, das angibt, ob der angegebene Ausdruck zu ausgewertet wird `True` .</span><span class="sxs-lookup"><span data-stu-id="fc435-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="fc435-195">Wenn Sie die `>` Operatoren und auf Zeichen folgen anwenden `<` , erfolgt der Vergleich mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fc435-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="fc435-196">Diese Reihenfolge kann von ihrer Gebiets Schema Einstellung abhängen.</span><span class="sxs-lookup"><span data-stu-id="fc435-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="fc435-197">Ob bei der Sortierung die Groß-/Kleinschreibung beachtet wird, hängt von der [Option Compare](../statements/option-compare-statement.md) -Einstellung ab.</span><span class="sxs-lookup"><span data-stu-id="fc435-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="fc435-198">Im vorherigen Beispiel gibt der erste Vergleich zurück, `False` und die restlichen Vergleiche geben zurück `True` .</span><span class="sxs-lookup"><span data-stu-id="fc435-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc435-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc435-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="fc435-200">=-Operator</span><span class="sxs-lookup"><span data-stu-id="fc435-200">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="fc435-201">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc435-201">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="fc435-202">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="fc435-202">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="fc435-203">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="fc435-203">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="fc435-204">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc435-204">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
