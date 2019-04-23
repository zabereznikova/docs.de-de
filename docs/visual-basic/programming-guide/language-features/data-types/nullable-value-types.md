---
title: Auf NULL festlegbare Werttypen – Visual Basic
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
ms.openlocfilehash: d17d2ad3fd99c6d563c21ddd646396ccb1c1ca48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58921311"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="7ecfc-102">Auf NULL festlegbare Werttypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ecfc-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="7ecfc-103">In einigen Fällen arbeiten Sie mit einem Werttyp, der nicht über einen definierten Wert unter bestimmten Umständen verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="7ecfc-104">Z. B. möglicherweise ein Feld in einer Datenbank zu unterscheiden, dass einen Wert zugewiesen, der sinnvoll ist, ohne dass einen Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="7ecfc-105">Werttypen können erweitert werden, um entweder die normalen Werte oder ein null-Wert.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="7ecfc-106">Eine solche Erweiterung wird aufgerufen, eine *nullable-Typ*.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="7ecfc-107">Jede nullable-Typ erstellt wird, von der generischen <xref:System.Nullable%601> Struktur.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="7ecfc-108">Nehmen Sie eine Datenbank, die geschäftliche Aktivitäten nachverfolgt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="7ecfc-109">Das folgende Beispiel erstellt eine auf NULL festlegbare `Boolean` geben und deklariert eine Variable dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="7ecfc-110">Sie können die Deklaration gibt drei Möglichkeiten zum Schreiben:</span><span class="sxs-lookup"><span data-stu-id="7ecfc-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="7ecfc-111">Die Variable `ridesBusToWork` kann einen Wert von aufzunehmen `True`, einen Wert von `False`, oder überhaupt kein Wert.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="7ecfc-112">Der anfängliche Standardwert ist kein Wert, der bedeuten in diesem Fall, dass sich die Informationen noch nicht für diese Person abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="7ecfc-113">Im Gegensatz dazu `False` bedeuten, dass sich die Informationen abgerufen wurden und die Person, die nicht mit den Bus zur Arbeit kommt.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="7ecfc-114">Sie können Variablen und Eigenschaften mit auf NULL festlegbare Typen deklarieren, und Sie können ein Array mit Elementen von einem nullable-Typ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="7ecfc-115">Sie können Prozeduren mit nullable-Typen als Parameter deklarieren, und Sie können einen nullable-Typ von Zurückgeben einer `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="7ecfc-116">Sie können keinen nullable-Typ in einen Verweistyp handelt, z. B. ein Array ist, erstellen eine `String`, oder eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="7ecfc-117">Der zugrunde liegende Typ muss ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-117">The underlying type must be a value type.</span></span> <span data-ttu-id="7ecfc-118">Weitere Informationen finden Sie unter [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="7ecfc-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="7ecfc-119">Verwenden die Variable ein Nullable-Typ</span><span class="sxs-lookup"><span data-stu-id="7ecfc-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="7ecfc-120">Die wichtigsten Mitglieder von einem nullable-Typ werden die <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="7ecfc-121">Für eine Variable vom einen nullable-Typ <xref:System.Nullable%601.HasValue%2A> Aufschluss darüber, ob die Variable einen definierten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="7ecfc-122">Wenn <xref:System.Nullable%601.HasValue%2A> ist `True`, Sie können den Wert von lesen <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="7ecfc-123">Beachten Sie, dass beide <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> sind `ReadOnly` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="7ecfc-124">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="7ecfc-124">Default Values</span></span>

<span data-ttu-id="7ecfc-125">Wenn Sie eine Variable mit einem NULL-Werte zulässt, deklarieren die <xref:System.Nullable%601.HasValue%2A> Eigenschaft hat den Standardwert `False`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="7ecfc-126">Dies bedeutet, dass standardmäßig die Variable keinen definierten Wert statt des Standardwerts, der den zugrunde liegenden Werttyp hat.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="7ecfc-127">Im folgenden Beispiel ist die Variable `numberOfChildren` Anfangs hat keinen definierter Wert, obwohl den Standardwert der `Integer` ist 0.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="7ecfc-128">Ein null-Wert ist hilfreich, einen nicht definierten oder unbekannten Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="7ecfc-129">Wenn `numberOfChildren` deklariert wurde als `Integer`, es gäbe keine-Wert, der anzeigen kann, dass die Informationen zurzeit nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="7ecfc-130">Speichern von Werten</span><span class="sxs-lookup"><span data-stu-id="7ecfc-130">Storing Values</span></span>

<span data-ttu-id="7ecfc-131">Sie speichern einen Wert in einer Variablen oder die Eigenschaft einen nullable-Typ, auf die gewohnte Weise.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="7ecfc-132">Im folgende Beispiel wird die Variable ein Wert zugewiesen `numberOfChildren` im vorherigen Beispiel deklariert.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="7ecfc-133">Wenn eine Variable oder eine Eigenschaft einen nullable-Typ um einen definierten Wert enthält, können Sie es auf seinen ursprünglichen Zustand des ohne eines zugewiesenen Wert zurückgesetzt auslösen.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="7ecfc-134">Hierzu legen Sie die Variable oder Eigenschaft, um `Nothing`, wie im folgende Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="7ecfc-135">Sie können zwar zuweisen `Nothing` auf eine Variable eines Typs mit NULL-Werte zulässt, kann nicht für test `Nothing` mit dem Gleichheitszeichen.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="7ecfc-136">Vergleich, das Gleichheitszeichen verwendet `someVar = Nothing`, ergibt immer `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="7ecfc-137">Sie können des Wert der Variablentyps testen <xref:System.Nullable%601.HasValue%2A> -Eigenschaft für `False`, oder testen, indem die `Is` oder `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="7ecfc-138">Abrufen von Werten</span><span class="sxs-lookup"><span data-stu-id="7ecfc-138">Retrieving Values</span></span>

<span data-ttu-id="7ecfc-139">Sie sollten zunächst testen, zum Abrufen des Werts einer Variablen mit einem nullable-Typ der <xref:System.Nullable%601.HasValue%2A> Eigenschaft, um sicherzustellen, dass es sich um einen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="7ecfc-140">Wenn Sie versuchen, den Wert zu lesen bei <xref:System.Nullable%601.HasValue%2A> ist `False`, Visual Basic löst eine <xref:System.InvalidOperationException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="7ecfc-141">Das folgende Beispiel zeigt die empfohlene Methode zum Lesen der Variablen `numberOfChildren` von den vorherigen Beispielen.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="7ecfc-142">Vergleichen von Nullable-Typen</span><span class="sxs-lookup"><span data-stu-id="7ecfc-142">Comparing Nullable Types</span></span>

<span data-ttu-id="7ecfc-143">Wenn auf NULL festlegbare `Boolean` Variablen in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`, oder `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="7ecfc-144">Im folgenden finden Sie die Wahrheitstabelle für `And` und `Or`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="7ecfc-145">Da `b1` und `b2` haben jetzt drei mögliche Werte sind neun Kombinationen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="7ecfc-146">b1</span><span class="sxs-lookup"><span data-stu-id="7ecfc-146">b1</span></span>|<span data-ttu-id="7ecfc-147">b2</span><span class="sxs-lookup"><span data-stu-id="7ecfc-147">b2</span></span>|<span data-ttu-id="7ecfc-148">B1 und b2</span><span class="sxs-lookup"><span data-stu-id="7ecfc-148">b1 And b2</span></span>|<span data-ttu-id="7ecfc-149">b1 Or b2</span><span class="sxs-lookup"><span data-stu-id="7ecfc-149">b1 Or b2</span></span>|
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

<span data-ttu-id="7ecfc-150">Wenn der Wert, der eine boolesche Variable oder einen Ausdruck ist `Nothing`, es ist keines von beiden `true` noch `false`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="7ecfc-151">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="7ecfc-152">In diesem Beispiel `b1 And b2` ergibt `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="7ecfc-153">Daher die `Else` -Klausel ausgeführt wird, in den einzelnen `If` -Anweisung und die Ausgabe sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="7ecfc-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="7ecfc-154">`AndAlso` und `OrElse`, welche verwenden kurzschlussauswertung muss ihrer zweiten Operanden ausgewertet werden, wenn die erste ergibt `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="7ecfc-155">Weitergabe</span><span class="sxs-lookup"><span data-stu-id="7ecfc-155">Propagation</span></span>

<span data-ttu-id="7ecfc-156">Wenn eine oder beide der Operanden des eine Arithmetik, Vergleich, UMSCHALT oder einem Rollenporttyp-Vorgang ist NULL-Werte zulässt, ist das Ergebnis des Vorgangs auch NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="7ecfc-157">Wenn beide Operanden Werte verfügen, die nicht `Nothing`, der Vorgang erfolgt auf die zugrunde liegenden Werte der Operanden, als wäre keine nullable-Typ.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="7ecfc-158">Im folgenden Beispiel Variablen `compare1` und `sum1` implizit typisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="7ecfc-159">Wenn Sie den Mauszeiger darüber bewegen, sehen Sie sich, dass leitet der Compiler die nullable-Typen für beide Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="7ecfc-160">Wenn eine oder beide der Operanden einen Wert `Nothing`, das Ergebnis `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="7ecfc-161">Verwenden von Nullable-Typen mit Daten</span><span class="sxs-lookup"><span data-stu-id="7ecfc-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="7ecfc-162">Eine Datenbank ist eine der wichtigsten Quellen für die nullable-Typen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="7ecfc-163">Nicht alle Datenbankobjekte wird derzeit auf NULL festlegbare Typen unterstützt, aber die vom Designer generierten Tabellenadaptern.</span><span class="sxs-lookup"><span data-stu-id="7ecfc-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="7ecfc-164">Finden Sie unter [TableAdapter-Unterstützung für auf NULL festlegbare Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="7ecfc-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ecfc-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ecfc-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="7ecfc-166">Verwenden von Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="7ecfc-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="7ecfc-167">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7ecfc-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="7ecfc-168">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="7ecfc-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="7ecfc-169">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="7ecfc-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="7ecfc-170">Füllen von Datasets mit TableAdapters</span><span class="sxs-lookup"><span data-stu-id="7ecfc-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="7ecfc-171">If-Operator</span><span class="sxs-lookup"><span data-stu-id="7ecfc-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="7ecfc-172">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="7ecfc-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="7ecfc-173">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="7ecfc-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="7ecfc-174">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="7ecfc-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)