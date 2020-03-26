---
title: Auf NULL festlegbare Werttypen
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249681"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="00aad-102">Auf NULL festlegbare Werttypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00aad-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="00aad-103">Manchmal arbeiten Sie mit einem Werttyp, der unter bestimmten Umständen keinen definierten Wert hat.</span><span class="sxs-lookup"><span data-stu-id="00aad-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="00aad-104">Beispielsweise muss ein Feld in einer Datenbank möglicherweise unterscheiden, ob ein wertschätzender Wert zugewiesen ist und kein Wert zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="00aad-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="00aad-105">Werttypen können erweitert werden, um entweder ihre Normalwerte oder einen NULL-Wert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="00aad-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="00aad-106">Eine solche Erweiterung wird als *nullabler Typ*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="00aad-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="00aad-107">Jeder nullable Werttyp wird <xref:System.Nullable%601> aus der generischen Struktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="00aad-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="00aad-108">Betrachten Sie eine Datenbank, die arbeitsbezogene Aktivitäten nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="00aad-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="00aad-109">Im folgenden Beispiel wird `Boolean` ein nullabler Typ erstellt und eine Variable dieses Typs deklariert.</span><span class="sxs-lookup"><span data-stu-id="00aad-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="00aad-110">Sie können die Deklaration auf drei Arten schreiben:</span><span class="sxs-lookup"><span data-stu-id="00aad-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="00aad-111">Die `ridesBusToWork` Variable kann einen `True`Wert von `False`, einen Wert von oder gar keinen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="00aad-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="00aad-112">Sein anfänglicher Standardwert ist überhaupt kein Wert, was in diesem Fall bedeuten könnte, dass die Informationen für diese Person noch nicht abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="00aad-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="00aad-113">Im Gegensatz `False` dazu könnte bedeuten, dass die Informationen erhalten wurden und die Person nicht mit dem Bus zur Arbeit fährt.</span><span class="sxs-lookup"><span data-stu-id="00aad-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="00aad-114">Sie können Variablen und Eigenschaften mit nullablen Werttypen deklarieren und Sie können ein Array mit Elementen eines nullablen Werttyps deklarieren.</span><span class="sxs-lookup"><span data-stu-id="00aad-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="00aad-115">Sie können Prozeduren mit NULL-Werttypen als Parameter deklarieren und `Function` einen nullablen Werttyp aus einer Prozedur zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="00aad-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="00aad-116">Sie können keinen nullbaren Typ für einen Verweistyp wie ein Array, eine `String`oder eine Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="00aad-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="00aad-117">Der zugrunde liegende Typ muss ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="00aad-117">The underlying type must be a value type.</span></span> <span data-ttu-id="00aad-118">Weitere Informationen finden Sie unter [Werttypen und Referenztypen](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="00aad-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="00aad-119">Verwenden einer Nullbaren Typvariablen</span><span class="sxs-lookup"><span data-stu-id="00aad-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="00aad-120">Die wichtigsten Member eines nullbaren <xref:System.Nullable%601.HasValue%2A> Werttyps sind seine und <xref:System.Nullable%601.Value%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="00aad-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="00aad-121">Gibt für eine Variable des <xref:System.Nullable%601.HasValue%2A> Nullwerttyps an, ob die Variable einen definierten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="00aad-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="00aad-122">Wenn <xref:System.Nullable%601.HasValue%2A> `True`dies der Falle <xref:System.Nullable%601.Value%2A>ist, können Sie den Wert aus aus lesen.</span><span class="sxs-lookup"><span data-stu-id="00aad-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="00aad-123">Beachten Sie, <xref:System.Nullable%601.Value%2A> `ReadOnly` dass beides <xref:System.Nullable%601.HasValue%2A> und eigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="00aad-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="00aad-124">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="00aad-124">Default Values</span></span>

<span data-ttu-id="00aad-125">Wenn Sie eine Variable mit einem NULL-Werttyp deklarieren, hat ihre <xref:System.Nullable%601.HasValue%2A> Eigenschaft den Standardwert von `False`.</span><span class="sxs-lookup"><span data-stu-id="00aad-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="00aad-126">Dies bedeutet, dass die Variable standardmäßig keinen definierten Wert anstelle des Standardwerts des zugrunde liegenden Werttyps hat.</span><span class="sxs-lookup"><span data-stu-id="00aad-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="00aad-127">Im folgenden Beispiel hat `numberOfChildren` die Variable zunächst keinen definierten Wert, `Integer` obwohl der Standardwert des Typs 0 ist.</span><span class="sxs-lookup"><span data-stu-id="00aad-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="00aad-128">Ein NULL-Wert ist nützlich, um einen nicht definierten oder unbekannten Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="00aad-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="00aad-129">Wenn `numberOfChildren` als `Integer`deklariert worden wäre, gäbe es keinen Wert, der darauf hinweisen könnte, dass die Informationen derzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00aad-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="00aad-130">Speichern von Werten</span><span class="sxs-lookup"><span data-stu-id="00aad-130">Storing Values</span></span>

<span data-ttu-id="00aad-131">Sie speichern einen Wert in einer Variablen oder Eigenschaft eines NULL-Werttyps auf die typische Weise.</span><span class="sxs-lookup"><span data-stu-id="00aad-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="00aad-132">Im folgenden Beispiel wird der `numberOfChildren` im vorherigen Beispiel deklarierten Variablen ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="00aad-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="00aad-133">Wenn eine Variable oder Eigenschaft eines NULL-Wert-Typs einen definierten Wert enthält, können Sie dazu führen, dass sie in den Anfangszustand zurückgesetzt wird, in dem kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="00aad-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="00aad-134">Dazu legen Sie die Variable `Nothing`oder Eigenschaft auf , wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="00aad-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="00aad-135">Obwohl Sie `Nothing` einer Variablen des Nullwerttyps zuweisen können, `Nothing` können Sie sie nicht mit dem Gleichheitszeichen testen.</span><span class="sxs-lookup"><span data-stu-id="00aad-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="00aad-136">Vergleich, der das `someVar = Nothing`Gleichheitszeichen verwendet, wird immer zu `Nothing`ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="00aad-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="00aad-137">Sie können <xref:System.Nullable%601.HasValue%2A> die Eigenschaft der `False`Variablen für testen `Is` `IsNot` oder mit dem Operator oder testen.</span><span class="sxs-lookup"><span data-stu-id="00aad-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="00aad-138">Abrufen von Werten</span><span class="sxs-lookup"><span data-stu-id="00aad-138">Retrieving Values</span></span>

<span data-ttu-id="00aad-139">Um den Wert einer Variablen eines NULL-Wert-Typs <xref:System.Nullable%601.HasValue%2A> abzurufen, sollten Sie zuerst ihre Eigenschaft testen, um zu bestätigen, dass sie einen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="00aad-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="00aad-140">Wenn Sie versuchen, den <xref:System.Nullable%601.HasValue%2A> `False`Wert zu lesen, wenn es ist, löst Visual Basic eine <xref:System.InvalidOperationException> Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="00aad-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="00aad-141">Das folgende Beispiel zeigt die empfohlene `numberOfChildren` Methode zum Lesen der Variablen der vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="00aad-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="00aad-142">Vergleichen von nullierbaren Typen</span><span class="sxs-lookup"><span data-stu-id="00aad-142">Comparing Nullable Types</span></span>

<span data-ttu-id="00aad-143">`Boolean` Wenn nullable Variablen in booleschen Ausdrücken `True` `False`verwendet `Nothing`werden, kann das Ergebnis , oder sein.</span><span class="sxs-lookup"><span data-stu-id="00aad-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="00aad-144">Im Folgenden finden Sie `And` `Or`die Wahrheitstabelle für und .</span><span class="sxs-lookup"><span data-stu-id="00aad-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="00aad-145">Da `b1` `b2` und jetzt drei mögliche Werte haben, gibt es neun Kombinationen zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="00aad-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="00aad-146">b1</span><span class="sxs-lookup"><span data-stu-id="00aad-146">b1</span></span>|<span data-ttu-id="00aad-147">B2</span><span class="sxs-lookup"><span data-stu-id="00aad-147">b2</span></span>|<span data-ttu-id="00aad-148">b1 Und b2</span><span class="sxs-lookup"><span data-stu-id="00aad-148">b1 And b2</span></span>|<span data-ttu-id="00aad-149">b1 Oder b2</span><span class="sxs-lookup"><span data-stu-id="00aad-149">b1 Or b2</span></span>|
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

<span data-ttu-id="00aad-150">Wenn der Wert einer booleschen `Nothing`Variablen oder `true` `false`eines Ausdrucks ist, ist er weder noch .</span><span class="sxs-lookup"><span data-stu-id="00aad-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="00aad-151">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="00aad-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="00aad-152">In diesem `b1 And b2` Beispiel werden `Nothing`Werte in ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="00aad-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="00aad-153">Daher wird die `Else` Klausel in jeder `If` Anweisung ausgeführt, und die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="00aad-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="00aad-154">`AndAlso`und `OrElse`, die kurzschlussauswertung verwenden, müssen ihre zweiten Operanden `Nothing`bewerten, wenn der erste auf ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="00aad-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="00aad-155">Weitergabe</span><span class="sxs-lookup"><span data-stu-id="00aad-155">Propagation</span></span>

<span data-ttu-id="00aad-156">Wenn einer oder beide Operanden eines Arithmetischen, Vergleichs-, Verschiebungs- oder Typvorgangs ein NULL-Werttyp ist, ist das Ergebnis des Vorgangs auch ein NULL-Werttyp.</span><span class="sxs-lookup"><span data-stu-id="00aad-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="00aad-157">Wenn beide Operanden Werte `Nothing`haben, die nicht sind, wird der Vorgang für die zugrunde liegenden Werte der Operanden ausgeführt, als ob keines von beiden ein NULL-Werttyp wäre.</span><span class="sxs-lookup"><span data-stu-id="00aad-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="00aad-158">Im folgenden Beispiel `compare1` `sum1` werden Variablen implizit eingegeben.</span><span class="sxs-lookup"><span data-stu-id="00aad-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="00aad-159">Wenn Sie den Mauszeiger darüber bewegen, werden Sie sehen, dass der Compiler für beide nullable Werttypen ableitet.</span><span class="sxs-lookup"><span data-stu-id="00aad-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="00aad-160">Wenn einer oder beide Operanden `Nothing`den Wert `Nothing`von haben, wird das Ergebnis .</span><span class="sxs-lookup"><span data-stu-id="00aad-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="00aad-161">Verwenden von Null-Typen mit Daten</span><span class="sxs-lookup"><span data-stu-id="00aad-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="00aad-162">Eine Datenbank ist einer der wichtigsten Orte für die Verwendung von NULL-Werttypen.</span><span class="sxs-lookup"><span data-stu-id="00aad-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="00aad-163">Nicht alle Datenbankobjekte unterstützen derzeit nullfähige Werttypen, aber die vom Designer generierten Tabellenadapter.</span><span class="sxs-lookup"><span data-stu-id="00aad-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="00aad-164">Siehe [TableAdapter-Unterstützung für nullfähige Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="00aad-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="00aad-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00aad-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="00aad-166">Datentypen</span><span class="sxs-lookup"><span data-stu-id="00aad-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="00aad-167">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="00aad-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="00aad-168">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="00aad-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="00aad-169">Füllen von Datasets mit TableAdapters</span><span class="sxs-lookup"><span data-stu-id="00aad-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="00aad-170">If-Operator</span><span class="sxs-lookup"><span data-stu-id="00aad-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="00aad-171">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="00aad-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="00aad-172">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="00aad-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="00aad-173">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="00aad-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="00aad-174">Nullable Wertetypen (C-Wert)</span><span class="sxs-lookup"><span data-stu-id="00aad-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
