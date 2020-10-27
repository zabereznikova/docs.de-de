---
title: 'Tupeltypen: C#-Referenz'
description: 'Enthält Informationen zu C#-Tupeln: Einfache Datenstrukturen, die Sie verwenden können, um lose zusammenhängende Datenelemente zu gruppieren.'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: d996c7afecba1b58bfd8337fa444fd71790dd482
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471771"
---
# <a name="tuple-types-c-reference"></a><span data-ttu-id="ce75e-103">Tupeltypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ce75e-103">Tuple types (C# reference)</span></span>

<span data-ttu-id="ce75e-104">Das Feature *Tupel* ist in C# 7.0 und höher verfügbar und bietet eine überschaubare Syntax zum Gruppieren von mehreren Datenelementen in einer einfachen Datenstruktur.</span><span class="sxs-lookup"><span data-stu-id="ce75e-104">Available in C# 7.0 and later, the *tuples* feature provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="ce75e-105">Im folgenden Beispiel wird veranschaulicht, wie Sie eine Tupelvariable deklarieren, initialisieren und dafür auf die zugehörigen Datenmember zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="ce75e-105">The following example shows how you can declare a tuple variable, initialize it, and access its data members:</span></span>

[!code-csharp-interactive[tuple intro](snippets/shared/ValueTuples.cs#Introduction)]

<span data-ttu-id="ce75e-106">Wie im obigen Beispiel zu sehen ist, geben Sie zum Definieren eines Tupeltyps die Typen aller Datenmember und optional die [Feldnamen](#tuple-field-names) an.</span><span class="sxs-lookup"><span data-stu-id="ce75e-106">As the preceding example shows, to define a tuple type, you specify types of all its data members and, optionally, the [field names](#tuple-field-names).</span></span> <span data-ttu-id="ce75e-107">Sie können keine Methoden in einem Tupeltyp definieren, aber Sie können die von .NET bereitgestellten Methoden verwenden. Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ce75e-107">You cannot define methods in a tuple type, but you can use the methods provided by .NET, as the following example shows:</span></span>

[!code-csharp-interactive[tuple methods](snippets/shared/ValueTuples.cs#MethodOnTuples)]

<span data-ttu-id="ce75e-108">Ab C# 7.3 unterstützen Tupeltypen die [Gleichheitsoperatoren](../operators/equality-operators.md) `==` und `!=`.</span><span class="sxs-lookup"><span data-stu-id="ce75e-108">Beginning with C# 7.3, tuple types support [equality operators](../operators/equality-operators.md) `==` and `!=`.</span></span> <span data-ttu-id="ce75e-109">Weitere Informationen finden Sie im Abschnitt [Tupelgleichheit](#tuple-equality).</span><span class="sxs-lookup"><span data-stu-id="ce75e-109">For more information, see the [Tuple equality](#tuple-equality) section.</span></span>

<span data-ttu-id="ce75e-110">Tupeltypen sind [Werttypen](value-types.md), und Tupelelemente sind öffentliche Felder.</span><span class="sxs-lookup"><span data-stu-id="ce75e-110">Tuple types are [value types](value-types.md); tuple elements are public fields.</span></span> <span data-ttu-id="ce75e-111">Bei Tupeln handelt es sich also um *veränderliche* Werttypen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-111">That makes tuples *mutable* value types.</span></span>

> [!NOTE]
> <span data-ttu-id="ce75e-112">Für das Feature „Tupel“ werden der Typ <xref:System.ValueTuple?displayProperty=nameWithType> und die zugehörigen generischen Typen (z. B. <xref:System.ValueTuple%602?displayProperty=nameWithType>) benötigt. Sie sind in .NET Core sowie in .NET Framework 4.7 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce75e-112">The tuples feature requires the <xref:System.ValueTuple?displayProperty=nameWithType> type and related generic types (for example, <xref:System.ValueTuple%602?displayProperty=nameWithType>), which are available in .NET Core and .NET Framework 4.7 and later.</span></span> <span data-ttu-id="ce75e-113">Fügen Sie dem Projekt das NuGet-Paket [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) hinzu, wenn Sie Tupel in einem Projekt nutzen möchten, das auf .NET Framework 4.6.2 oder früher ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ce75e-113">To use tuples in a project that targets .NET Framework 4.6.2 or earlier, add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) to the project.</span></span>

<span data-ttu-id="ce75e-114">Sie können Tupel mit einer beliebig großen Anzahl von Elementen definieren:</span><span class="sxs-lookup"><span data-stu-id="ce75e-114">You can define tuples with an arbitrary large number of elements:</span></span>

[!code-csharp-interactive[large tuple](snippets/shared/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a><span data-ttu-id="ce75e-115">Anwendungsfälle von Tupeln</span><span class="sxs-lookup"><span data-stu-id="ce75e-115">Use cases of tuples</span></span>

<span data-ttu-id="ce75e-116">Einer der häufigsten Anwendungsfälle für Tupel ist die Verwendung als Methodenrückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="ce75e-116">One of the most common use cases of tuples is as a method return type.</span></span> <span data-ttu-id="ce75e-117">Anstatt [`out`-Methodenparameter](../keywords/out-parameter-modifier.md) zu definieren, können Sie also Methodenergebnisse in einem Tupelrückgabetyp gruppieren. Dies ist im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ce75e-117">That is, instead of defining [`out` method parameters](../keywords/out-parameter-modifier.md), you can group method results in a tuple return type, as the following example shows:</span></span>

[!code-csharp-interactive[multiple method outputs](snippets/shared/ValueTuples.cs#MultipleReturns)]

<span data-ttu-id="ce75e-118">Wie Sie im obigen Beispiel sehen, können Sie direkt mit der zurückgegebenen Tupelinstanz arbeiten oder sie in separate Variablen [dekonstruieren](#tuple-assignment-and-deconstruction).</span><span class="sxs-lookup"><span data-stu-id="ce75e-118">As the preceding example shows, you can work with the returned tuple instance directly or [deconstruct](#tuple-assignment-and-deconstruction) it in separate variables.</span></span>

<span data-ttu-id="ce75e-119">Sie können Tupeltypen auch anstelle von [anonymen Typen](../../programming-guide/classes-and-structs/anonymous-types.md) verwenden, z. B. in LINQ-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-119">You can also use tuple types instead of [anonymous types](../../programming-guide/classes-and-structs/anonymous-types.md); for example, in LINQ queries.</span></span> <span data-ttu-id="ce75e-120">Weitere Informationen finden Sie unter [Auswählen zwischen anonymen Typen und Tupeltypen](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span><span class="sxs-lookup"><span data-stu-id="ce75e-120">For more information, see [Choosing between anonymous and tuple types](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span></span>

<span data-ttu-id="ce75e-121">Normalerweise verwenden Sie Tupel, um lose zusammengehörende Datenelemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ce75e-121">Typically, you use tuples to group loosely related data elements.</span></span> <span data-ttu-id="ce75e-122">Dies ist normalerweise bei privaten und internen Hilfsmethoden hilfreich.</span><span class="sxs-lookup"><span data-stu-id="ce75e-122">That is usually useful within private and internal utility methods.</span></span> <span data-ttu-id="ce75e-123">Erwägen Sie bei Verwendung einer öffentlichen API, den Typ [Klasse](../keywords/class.md) oder [Struktur](struct.md) zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ce75e-123">In the case of public API, consider defining a [class](../keywords/class.md) or a [structure](struct.md) type.</span></span>

## <a name="tuple-field-names"></a><span data-ttu-id="ce75e-124">Tupelfeldnamen</span><span class="sxs-lookup"><span data-stu-id="ce75e-124">Tuple field names</span></span>

<span data-ttu-id="ce75e-125">Sie können die Namen von Tupelfeldern entweder in einem Ausdruck für die Tupelinitialisierung oder in der Definition eines Tupeltyps explizit angeben. Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ce75e-125">You can explicitly specify the names of tuple fields either in a tuple initialization expression or in the definition of a tuple type, as the following example shows:</span></span>

[!code-csharp-interactive[explicit field names](snippets/shared/ValueTuples.cs#ExplicitFieldNames)]

<span data-ttu-id="ce75e-126">Ab C# 7.1 gilt Folgendes: Wenn Sie keinen Feldnamen angeben, wird er ggf. vom Namen der entsprechenden Variablen in einem Ausdruck für die Tupelinitialisierung abgeleitet (wie im folgenden Beispiel):</span><span class="sxs-lookup"><span data-stu-id="ce75e-126">Beginning with C# 7.1, if you don't specify a field name, it may be inferred from the name of the corresponding variable in a tuple initialization expression, as the following example shows:</span></span>

[!code-csharp-interactive[inferred field names](snippets/shared/ValueTuples.cs#InferFieldNames)]

<span data-ttu-id="ce75e-127">Dies wird als Tupel-Projektionsinitialisierer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ce75e-127">That's known as tuple projection initializers.</span></span> <span data-ttu-id="ce75e-128">Der Name einer Variablen wird in den folgenden Fällen nicht auf einen Tupelfeldnamen projiziert:</span><span class="sxs-lookup"><span data-stu-id="ce75e-128">The name of a variable isn't projected onto a tuple field name in the following cases:</span></span>

- <span data-ttu-id="ce75e-129">Der Kandidatenname ist ein Membername eines Tupeltyps, z. B. `Item3`, `ToString` oder `Rest`.</span><span class="sxs-lookup"><span data-stu-id="ce75e-129">The candidate name is a member name of a tuple type, for example, `Item3`, `ToString`, or `Rest`.</span></span>
- <span data-ttu-id="ce75e-130">Beim Namen des Kandidaten handelt es sich um das Duplikat des expliziten oder impliziten Feldnamens eines anderen Tupels.</span><span class="sxs-lookup"><span data-stu-id="ce75e-130">The candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="ce75e-131">In diesen Fällen geben Sie entweder explizit den Namen eines Felds an oder greifen über den Standardnamen auf ein Feld zu.</span><span class="sxs-lookup"><span data-stu-id="ce75e-131">In those cases you either explicitly specify the name of a field or access a field by its default name.</span></span>

<span data-ttu-id="ce75e-132">Die Standardnamen von Tupelfeldern lauten `Item1`, `Item2`, `Item3` usw.</span><span class="sxs-lookup"><span data-stu-id="ce75e-132">The default names of tuple fields are `Item1`, `Item2`, `Item3` and so on.</span></span> <span data-ttu-id="ce75e-133">Den Standardnamen eines Felds können Sie immer verwenden. Dies gilt auch, wenn ein Feldname explizit angegeben oder abgeleitet wird (wie im folgenden Beispiel):</span><span class="sxs-lookup"><span data-stu-id="ce75e-133">You can always use the default name of a field, even when a field name is specified explicitly or inferred, as the following example shows:</span></span>

[!code-csharp-interactive[default field names](snippets/shared/ValueTuples.cs#DefaultFieldNames)]

<span data-ttu-id="ce75e-134">Bei der [Tupelzuweisung](#tuple-assignment-and-deconstruction) und bei [Vergleichen der Tupelgleichheit](#tuple-equality) werden Feldnamen nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ce75e-134">[Tuple assignment](#tuple-assignment-and-deconstruction) and [tuple equality comparisons](#tuple-equality) don't take field names into account.</span></span>

<span data-ttu-id="ce75e-135">Zur Kompilierzeit ersetzt der Compiler die nicht dem Standard entsprechenden Felder durch die jeweiligen Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-135">At compile time, the compiler replaces non-default field names with the corresponding default names.</span></span> <span data-ttu-id="ce75e-136">Daher sind explizit angegebene oder abgeleitete Feldnamen zur Laufzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce75e-136">As a result, explicitly specified or inferred field names aren't available at run time.</span></span>

## <a name="tuple-assignment-and-deconstruction"></a><span data-ttu-id="ce75e-137">Tupelzuweisung und -dekonstruktion</span><span class="sxs-lookup"><span data-stu-id="ce75e-137">Tuple assignment and deconstruction</span></span>

<span data-ttu-id="ce75e-138">C# unterstützt die Zuweisung zwischen Tupeltypen, die die beiden folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ce75e-138">C# supports assignment between tuple types that satisfy both of the following conditions:</span></span>

- <span data-ttu-id="ce75e-139">Beide Tupeltypen haben die gleiche Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-139">both tuple types have the same number of elements</span></span>
- <span data-ttu-id="ce75e-140">Für jede Tupelposition ist der Typ des rechten Tupelelements mit dem Typ des entsprechenden linken Tupelelements identisch oder implizit konvertierbar.</span><span class="sxs-lookup"><span data-stu-id="ce75e-140">for each tuple position, the type of the right-hand tuple element is the same as or implicitly convertible to the type of the corresponding left-hand tuple element</span></span>

<span data-ttu-id="ce75e-141">Die Werte von Tupelelementen werden gemäß der Reihenfolge der Tupelelemente zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-141">Tuple element values are assigned following the order of tuple elements.</span></span> <span data-ttu-id="ce75e-142">Die Namen von Tupelfeldern werden ignoriert und nicht zugewiesen. Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ce75e-142">The names of tuple fields are ignored and not assigned, as the following example shows:</span></span>

[!code-csharp-interactive[tuple assignment](snippets/shared/ValueTuples.cs#Assignment)]

<span data-ttu-id="ce75e-143">Sie können auch den Zuweisungsoperator `=` verwenden, um eine Tupelinstanz in separate Variablen zu *dekonstruieren* .</span><span class="sxs-lookup"><span data-stu-id="ce75e-143">You can also use the assignment operator `=` to *deconstruct* a tuple instance in separate variables.</span></span> <span data-ttu-id="ce75e-144">Hierfür können Sie eine der folgenden Vorgehensweisen wählen:</span><span class="sxs-lookup"><span data-stu-id="ce75e-144">You can do that in one of the following ways:</span></span>

- <span data-ttu-id="ce75e-145">Explizites Deklarieren des Typs jeder Variablen in Klammern:</span><span class="sxs-lookup"><span data-stu-id="ce75e-145">Explicitly declare the type of each variable inside parentheses:</span></span>

  [!code-csharp-interactive[specify types of variables](snippets/shared/ValueTuples.cs#DeconstructExplicit)]

- <span data-ttu-id="ce75e-146">Verwenden des Schlüsselworts `var` außerhalb der Klammern, um implizit typisierte Variablen zu deklarieren und die Typen vom Compiler ableiten zu lassen:</span><span class="sxs-lookup"><span data-stu-id="ce75e-146">Use the `var` keyword outside the parentheses to declare implicitly typed variables and let the compiler infer their types:</span></span>

  [!code-csharp-interactive[implicitly typed variables](snippets/shared/ValueTuples.cs#DeconstructVar)]

- <span data-ttu-id="ce75e-147">Verwenden von vorhandenen Variablen:</span><span class="sxs-lookup"><span data-stu-id="ce75e-147">Use existing variables:</span></span>

  [!code-csharp-interactive[existing variables](snippets/shared/ValueTuples.cs#DeconstructExisting)]

<span data-ttu-id="ce75e-148">Weitere Informationen zur Dekonstruktion von Tupeln und anderen Typen finden Sie unter [Dekonstruieren von Tupeln und anderen Typen](../../deconstruct.md).</span><span class="sxs-lookup"><span data-stu-id="ce75e-148">For more information about deconstruction of tuples and other types, see [Deconstructing tuples and other types](../../deconstruct.md).</span></span>

## <a name="tuple-equality"></a><span data-ttu-id="ce75e-149">Tupelgleichheit</span><span class="sxs-lookup"><span data-stu-id="ce75e-149">Tuple equality</span></span>

<span data-ttu-id="ce75e-150">Ab C# 7.3 unterstützen Tupeltypen die Operatoren `==` und `!=`.</span><span class="sxs-lookup"><span data-stu-id="ce75e-150">Beginning with C# 7.3, tuple types support the `==` and `!=` operators.</span></span> <span data-ttu-id="ce75e-151">Mit diesen Operatoren werden Member des linken Operanden gemäß der Reihenfolge der Tupelelemente mit den entsprechenden Membern des rechten Operanden verglichen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-151">These operators compare members of the left-hand operand with the corresponding members of the right-hand operand following the order of tuple elements.</span></span>

[!code-csharp-interactive[tuple equality](snippets/shared/ValueTuples.cs#TupleEquality)]

<span data-ttu-id="ce75e-152">Wie im obigen Beispiel zu sehen ist, werden Tupelfeldnamen bei Operationen mit `==` und `!=` nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ce75e-152">As the preceding example shows, the `==` and `!=` operations don't take into account tuple field names.</span></span>

<span data-ttu-id="ce75e-153">Zwei Tupel sind vergleichbar, wenn die beiden folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="ce75e-153">Two tuples are comparable when both of the following conditions are satisfied:</span></span>

- <span data-ttu-id="ce75e-154">Beide Tupel weisen die gleiche Anzahl von Elementen auf.</span><span class="sxs-lookup"><span data-stu-id="ce75e-154">Both tuples have the same number of elements.</span></span> <span data-ttu-id="ce75e-155">`t1 != t2` wird beispielsweise nicht kompiliert, wenn `t1` und `t2` über eine unterschiedliche Anzahl von Elementen verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce75e-155">For example, `t1 != t2` doesn't compile if `t1` and `t2` have different numbers of elements.</span></span>
- <span data-ttu-id="ce75e-156">Für jede Tupelposition können die entsprechenden Elemente der linken und rechten Tupeloperanden mit den Operatoren `==` und `!=` verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="ce75e-156">For each tuple position, the corresponding elements from the left-hand and right-hand tuple operands are comparable with the `==` and `!=` operators.</span></span> <span data-ttu-id="ce75e-157">`(1, (2, 3)) == ((1, 2), 3)` wird beispielsweise nicht kompiliert, weil `1` nicht mit `(1, 2)` vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="ce75e-157">For example, `(1, (2, 3)) == ((1, 2), 3)` doesn't compile because `1` is not comparable with `(1, 2)`.</span></span>

<span data-ttu-id="ce75e-158">Die Operatoren `==` und `!=` vergleichen Tupel per „Kurzschluss“.</span><span class="sxs-lookup"><span data-stu-id="ce75e-158">The `==` and `!=` operators compare tuples in short-circuiting way.</span></span> <span data-ttu-id="ce75e-159">Dies bedeutet, dass eine Operation sofort angehalten wird, wenn ein Paar mit ungleichen Elementen erkannt oder das Ende von Tupeln erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ce75e-159">That is, an operation stops as soon as it meets a pair of non equal elements or reaches the ends of tuples.</span></span> <span data-ttu-id="ce75e-160">Bevor ein Vergleich durchgeführt wird, werden aber *alle* Tupelelemente ausgewertet. Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ce75e-160">However, before any comparison, *all* tuple elements are evaluated, as the following example shows:</span></span>

[!code-csharp-interactive[tuple element evaluation](snippets/shared/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a><span data-ttu-id="ce75e-161">Tupel als out-Parameter</span><span class="sxs-lookup"><span data-stu-id="ce75e-161">Tuples as out parameters</span></span>

<span data-ttu-id="ce75e-162">Normalerweise gestalten Sie eine Methode, die [`out`-Parameter](../keywords/out-parameter-modifier.md) enthält, in eine Methode um, die ein Tupel zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ce75e-162">Typically, you refactor a method that has [`out` parameters](../keywords/out-parameter-modifier.md) into a method that returns a tuple.</span></span> <span data-ttu-id="ce75e-163">Es gibt aber auch Fälle, in denen ein `out`-Parameter einen Tupeltyp aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="ce75e-163">However, there are cases in which an `out` parameter can be of a tuple type.</span></span> <span data-ttu-id="ce75e-164">Im folgenden Beispiel wird veranschaulicht, wie Sie Tupel als `out`-Parameter verwenden:</span><span class="sxs-lookup"><span data-stu-id="ce75e-164">The following example shows how to work with tuples as `out` parameters:</span></span>

[!code-csharp-interactive[tuple as out parameter](snippets/shared/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a><span data-ttu-id="ce75e-165">Vergleich von Tupeln und `System.Tuple`</span><span class="sxs-lookup"><span data-stu-id="ce75e-165">Tuples vs `System.Tuple`</span></span>

<span data-ttu-id="ce75e-166">C#-Tupel, die auf <xref:System.ValueTuple?displayProperty=nameWithType>-Typen basieren, unterscheiden sich von Tupeln, die auf <xref:System.Tuple?displayProperty=nameWithType>-Typen basieren.</span><span class="sxs-lookup"><span data-stu-id="ce75e-166">C# tuples, which are backed by <xref:System.ValueTuple?displayProperty=nameWithType> types, are different from tuples that are represented by <xref:System.Tuple?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="ce75e-167">Es gibt die folgenden Hauptunterschiede:</span><span class="sxs-lookup"><span data-stu-id="ce75e-167">The main differences are as follows:</span></span>

- <span data-ttu-id="ce75e-168">Bei `ValueTuple`-Typen handelt es sich um [Werttypen](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="ce75e-168">`ValueTuple` types are [value types](value-types.md).</span></span> <span data-ttu-id="ce75e-169">`Tuple`-Typen sind [Verweistypen](../keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ce75e-169">`Tuple` types are [reference types](../keywords/reference-types.md).</span></span>
- <span data-ttu-id="ce75e-170">`ValueTuple`-Typen sind veränderlich.</span><span class="sxs-lookup"><span data-stu-id="ce75e-170">`ValueTuple` types are mutable.</span></span> <span data-ttu-id="ce75e-171">`Tuple`-Typen sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="ce75e-171">`Tuple` types are immutable.</span></span>
- <span data-ttu-id="ce75e-172">Datenmember von `ValueTuple`-Typen sind Felder.</span><span class="sxs-lookup"><span data-stu-id="ce75e-172">Data members of `ValueTuple` types are fields.</span></span> <span data-ttu-id="ce75e-173">Datenmember von `Tuple`-Typen sind Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ce75e-173">Data members of `Tuple` types are properties.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ce75e-174">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ce75e-174">C# language specification</span></span>

<span data-ttu-id="ce75e-175">Weitere Informationen finden Sie in den folgenden Hinweisen zu Featurevorschlägen:</span><span class="sxs-lookup"><span data-stu-id="ce75e-175">For more information, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="ce75e-176">Ableiten von Tupelnamen (Tupel-Projektionsinitialisierer)</span><span class="sxs-lookup"><span data-stu-id="ce75e-176">Infer tuple names (aka. tuple projection initializers)</span></span>](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [<span data-ttu-id="ce75e-177">Unterstützung für `==` und `!=` in Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="ce75e-177">Support for `==` and `!=` on tuple types</span></span>](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a><span data-ttu-id="ce75e-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce75e-178">See also</span></span>

- [<span data-ttu-id="ce75e-179">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ce75e-179">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ce75e-180">Werttypen</span><span class="sxs-lookup"><span data-stu-id="ce75e-180">Value types</span></span>](value-types.md)
- [<span data-ttu-id="ce75e-181">Auswählen zwischen anonymen Typen und Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="ce75e-181">Choosing between anonymous and tuple types</span></span>](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
