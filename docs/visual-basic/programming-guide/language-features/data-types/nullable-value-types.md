---
title: Auf NULL festleg Bare Werttypen-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 1fb8f8d1657b8eab6b15858c2a6607cbde82e542
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732939"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="03c42-102">Auf NULL festlegbare Werttypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03c42-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="03c42-103">Manchmal arbeiten Sie mit einem Werttyp, der unter bestimmten Umständen keinen definierten Wert hat.</span><span class="sxs-lookup"><span data-stu-id="03c42-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="03c42-104">Beispielsweise muss ein Feld in einer Datenbank möglicherweise zwischen einem zugewiesenen Wert unterscheiden, der aussagekräftig ist und keinem zugewiesenen Wert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="03c42-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="03c42-105">Werttypen können so erweitert werden, dass Sie entweder Ihre normalen Werte oder einen NULL-Wert akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="03c42-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="03c42-106">Eine solche Erweiterung wird als Typ bezeichnet, der *NULL-Werte*zulässt.</span><span class="sxs-lookup"><span data-stu-id="03c42-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="03c42-107">Jeder Typ, der NULL-Werte zulässt, wird aus der generischen <xref:System.Nullable%601> Struktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="03c42-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="03c42-108">Stellen Sie sich eine Datenbank vor, die arbeitsbezogene Aktivitäten nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="03c42-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="03c42-109">Im folgenden Beispiel wird ein `Boolean` Typ erstellt, der NULL-Werte zulässt, und eine Variable dieses Typs deklariert.</span><span class="sxs-lookup"><span data-stu-id="03c42-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="03c42-110">Es gibt drei Möglichkeiten, die Deklaration zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="03c42-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="03c42-111">Die Variable `ridesBusToWork` kann den Wert `True`, den Wert `False`oder keinen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="03c42-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="03c42-112">Der anfängliche Standardwert ist überhaupt kein Wert, was in diesem Fall bedeuten könnte, dass die Informationen für diese Person noch nicht abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="03c42-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="03c42-113">Im Gegensatz dazu kann `False` bedeuten, dass die Informationen abgerufen wurden und die Person den Bus nicht zum Arbeiten fährt.</span><span class="sxs-lookup"><span data-stu-id="03c42-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="03c42-114">Sie können Variablen und Eigenschaften mit Typen deklarieren, die NULL-Werte zulassen, und Sie können ein Array mit Elementen eines Typs deklarieren, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="03c42-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="03c42-115">Sie können Prozeduren mit Typen, die NULL-Werte zulassen, als Parameter deklarieren und einen Typ, der NULL-Werte zulässt, aus einer `Function` Prozedur</span><span class="sxs-lookup"><span data-stu-id="03c42-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="03c42-116">Sie können einen Typ, der NULL-Werte zulässt, nicht für einen Referenztyp erstellen, z. b. ein Array, ein `String`oder eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="03c42-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="03c42-117">Der zugrunde liegende Typ muss ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="03c42-117">The underlying type must be a value type.</span></span> <span data-ttu-id="03c42-118">Weitere Informationen finden Sie unter [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="03c42-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="03c42-119">Verwenden einer Typvariablen, die NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="03c42-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="03c42-120">Die wichtigsten Member eines Typs, der NULL-Werte zulässt, sind die Eigenschaften <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="03c42-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="03c42-121">Für eine Variable eines Typs, der NULL-Werte zulässt, gibt <xref:System.Nullable%601.HasValue%2A> Aufschluss darüber, ob die Variable einen definierten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="03c42-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="03c42-122">Wenn <xref:System.Nullable%601.HasValue%2A> `True`ist, können Sie den Wert aus <xref:System.Nullable%601.Value%2A>lesen.</span><span class="sxs-lookup"><span data-stu-id="03c42-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="03c42-123">Beachten Sie, dass sowohl <xref:System.Nullable%601.HasValue%2A> als auch <xref:System.Nullable%601.Value%2A> `ReadOnly` Eigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="03c42-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="03c42-124">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="03c42-124">Default Values</span></span>

<span data-ttu-id="03c42-125">Wenn Sie eine Variable mit einem Typ deklarieren, der NULL-Werte zulässt, hat die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft den Standardwert `False`.</span><span class="sxs-lookup"><span data-stu-id="03c42-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="03c42-126">Dies bedeutet, dass die Variable standardmäßig keinen definierten Wert anstelle des Standardwerts des zugrunde liegenden Werttyps aufweist.</span><span class="sxs-lookup"><span data-stu-id="03c42-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="03c42-127">Im folgenden Beispiel hat die Variable `numberOfChildren` anfänglich keinen definierten Wert, obwohl der Standardwert des `Integer` Typs 0 ist.</span><span class="sxs-lookup"><span data-stu-id="03c42-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="03c42-128">Ein NULL-Wert ist nützlich, um einen nicht definierten oder unbekannten Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03c42-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="03c42-129">Wenn `numberOfChildren` als `Integer`deklariert wurde, wäre kein Wert vorhanden, der darauf hindeuten kann, dass die Informationen zurzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="03c42-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="03c42-130">Speichern von Werten</span><span class="sxs-lookup"><span data-stu-id="03c42-130">Storing Values</span></span>

<span data-ttu-id="03c42-131">Sie speichern einen Wert in einer Variablen oder Eigenschaft eines Typs, der NULL-Werte zulässt, auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="03c42-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="03c42-132">Im folgenden Beispiel wird der Variablen `numberOfChildren`, die im vorherigen Beispiel deklariert wurde, ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="03c42-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="03c42-133">Wenn eine Variable oder Eigenschaft eines Typs, der NULL-Werte zulässt, einen definierten Wert enthält, können Sie bewirken, dass Sie in den ursprünglichen Zustand zurückversetzt wird, dass kein Wert zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="03c42-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="03c42-134">Hierzu legen Sie die Variable oder Eigenschaft auf `Nothing`fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="03c42-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="03c42-135">Obwohl Sie `Nothing` einer Variablen eines Typs zuweisen können, der NULL-Werte zulässt, können Sie ihn nicht mit dem Gleichheitszeichen für `Nothing` testen.</span><span class="sxs-lookup"><span data-stu-id="03c42-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="03c42-136">Ein Vergleich, bei dem das Gleichheitszeichen (`someVar = Nothing`) verwendet wird, ergibt immer `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="03c42-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="03c42-137">Sie können die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft der Variablen für `False`testen oder mithilfe des Operators `Is` oder `IsNot` testen.</span><span class="sxs-lookup"><span data-stu-id="03c42-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="03c42-138">Abrufen von Werten</span><span class="sxs-lookup"><span data-stu-id="03c42-138">Retrieving Values</span></span>

<span data-ttu-id="03c42-139">Zum Abrufen des Werts einer Variablen eines Typs, der NULL-Werte zulässt, sollten Sie zunächst die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft testen, um zu bestätigen, dass Sie über einen Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="03c42-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="03c42-140">Wenn Sie versuchen, den Wert zu lesen, wenn <xref:System.Nullable%601.HasValue%2A> `False`ist, löst Visual Basic eine <xref:System.InvalidOperationException> Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="03c42-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="03c42-141">Das folgende Beispiel zeigt die empfohlene Vorgehensweise zum Lesen der Variablen `numberOfChildren` der vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="03c42-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="03c42-142">Vergleichen von Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="03c42-142">Comparing Nullable Types</span></span>

<span data-ttu-id="03c42-143">Wenn `Boolean` Variablen, die NULL-Werte zulassen, in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`oder `Nothing`sein.</span><span class="sxs-lookup"><span data-stu-id="03c42-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="03c42-144">Im folgenden finden Sie die Wahrheitstabelle für `And` und `Or`.</span><span class="sxs-lookup"><span data-stu-id="03c42-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="03c42-145">Da `b1` und `b2` nun drei mögliche Werte aufweisen, gibt es neun zu bewertende Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="03c42-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="03c42-146">Handelte</span><span class="sxs-lookup"><span data-stu-id="03c42-146">b1</span></span>|<span data-ttu-id="03c42-147">B2</span><span class="sxs-lookup"><span data-stu-id="03c42-147">b2</span></span>|<span data-ttu-id="03c42-148">B1 und B2</span><span class="sxs-lookup"><span data-stu-id="03c42-148">b1 And b2</span></span>|<span data-ttu-id="03c42-149">B1 oder B2</span><span class="sxs-lookup"><span data-stu-id="03c42-149">b1 Or b2</span></span>|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

<span data-ttu-id="03c42-150">Wenn der Wert einer booleschen Variablen oder eines Ausdrucks `Nothing`ist, ist er weder `true` noch `false`.</span><span class="sxs-lookup"><span data-stu-id="03c42-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="03c42-151">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="03c42-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="03c42-152">In diesem Beispiel ergibt `b1 And b2` `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="03c42-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="03c42-153">Folglich wird die `Else`-Klausel in jeder `If`-Anweisung ausgeführt, und die Ausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="03c42-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="03c42-154">`AndAlso` und `OrElse`, bei denen die Kurzschluss Auswertung verwendet wird, müssen die zweiten Operanden auswerten, wenn der erste zu `Nothing`ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="03c42-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="03c42-155">Weitergabe</span><span class="sxs-lookup"><span data-stu-id="03c42-155">Propagation</span></span>

<span data-ttu-id="03c42-156">Wenn einer der Operanden eines arithmetischen, Vergleichs-, Verschiebungs-oder typvorgangs NULL-Werte zulässt, kann das Ergebnis des Vorgangs ebenfalls NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="03c42-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="03c42-157">Wenn beide Operanden über Werte verfügen, die nicht `Nothing`sind, wird der Vorgang für die zugrunde liegenden Werte der Operanden ausgeführt, als wären keine NULL-Werte zulässig.</span><span class="sxs-lookup"><span data-stu-id="03c42-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="03c42-158">Im folgenden Beispiel werden Variablen `compare1` und `sum1` implizit eingegeben.</span><span class="sxs-lookup"><span data-stu-id="03c42-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="03c42-159">Wenn Sie den Mauszeiger darüber bewegen, sehen Sie, dass der Compiler Werte zulässt-Typen für beide ausleitet.</span><span class="sxs-lookup"><span data-stu-id="03c42-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="03c42-160">Wenn ein oder beide Operanden den Wert `Nothing`haben, wird das Ergebnis `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="03c42-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="03c42-161">Verwenden von Nullable-Typen mit Daten</span><span class="sxs-lookup"><span data-stu-id="03c42-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="03c42-162">Eine Datenbank ist einer der wichtigsten Orte für die Verwendung von Typen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="03c42-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="03c42-163">Nicht alle Datenbankobjekte unterstützen zurzeit Typen, die NULL-Werte zulassen, aber die vom Designer generierten Tabellen Adapter.</span><span class="sxs-lookup"><span data-stu-id="03c42-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="03c42-164">Siehe [TableAdapter-Unterstützung für Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types), die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="03c42-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="03c42-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03c42-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="03c42-166">Datentypen</span><span class="sxs-lookup"><span data-stu-id="03c42-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="03c42-167">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="03c42-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="03c42-168">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="03c42-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="03c42-169">Füllen von Datasets mit TableAdapters</span><span class="sxs-lookup"><span data-stu-id="03c42-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="03c42-170">If-Operator</span><span class="sxs-lookup"><span data-stu-id="03c42-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="03c42-171">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="03c42-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="03c42-172">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="03c42-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="03c42-173">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="03c42-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="03c42-174">Auf NULL festleg BareC#Werttypen ()</span><span class="sxs-lookup"><span data-stu-id="03c42-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
