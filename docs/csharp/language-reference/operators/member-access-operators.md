---
title: Operatoren für den Memberzugriff – C#-Referenz
description: Enthält Informationen zu C#-Operatoren, die Sie für den Zugriff auf Typmember verwenden können.
ms.date: 09/18/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: ba2a8cd4995b9baab2071d3fb3c7980e45565692
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038997"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="6716a-103">Operatoren für den Memberzugriff (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6716a-103">Member access operators (C# reference)</span></span>

<span data-ttu-id="6716a-104">Sie können die folgenden Operatoren zum Zugriff auf einen Typmember verwenden:</span><span class="sxs-lookup"><span data-stu-id="6716a-104">You can use the following operators when you access a type member:</span></span>

- <span data-ttu-id="6716a-105">[`.` (Memberzugriff)](#member-access-operator-): für den Zugriff auf einen Member eines Namespaces oder Typs</span><span class="sxs-lookup"><span data-stu-id="6716a-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="6716a-106">[`[]` (Zugriff auf Arrayelement oder Indexer) ](#indexer-operator-): Zugriff auf ein Arrayelement oder einen Typindexer</span><span class="sxs-lookup"><span data-stu-id="6716a-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="6716a-107">[`?.` und `?[]` (NULL-bedingte Operatoren)](#null-conditional-operators--and-): Ausführen eines Member- oder Elementzugriffs nur dann, wenn ein Operand ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="6716a-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="6716a-108">[`()` (Aufruf)](#invocation-operator-): Aufrufen einer Methode, auf die zugegriffen wurde, oder Aufrufen eines Delegaten</span><span class="sxs-lookup"><span data-stu-id="6716a-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="6716a-109">[`^` (Index vom Ende)](#index-from-end-operator-): Angeben, dass die Elementposition vom Ende einer Sequenz erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6716a-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="6716a-110">[`..` Bereich](#range-operator-): Angeben eines Bereichs von Indizes, mit dem ein Bereich von Sequenzelementen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6716a-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="6716a-111">Memberzugriffsoperator „.“</span><span class="sxs-lookup"><span data-stu-id="6716a-111">Member access operator .</span></span>

<span data-ttu-id="6716a-112">Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="6716a-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="6716a-113">Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6716a-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="6716a-114">Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6716a-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="6716a-115">Verwenden Sie eine [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.</span><span class="sxs-lookup"><span data-stu-id="6716a-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="6716a-116">Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6716a-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="6716a-117">Sie können auch `.` verwenden, um auf eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6716a-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="6716a-118">Indexeroperator []</span><span class="sxs-lookup"><span data-stu-id="6716a-118">Indexer operator []</span></span>

<span data-ttu-id="6716a-119">Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="6716a-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="6716a-120">Arrayzugriff</span><span class="sxs-lookup"><span data-stu-id="6716a-120">Array access</span></span>

<span data-ttu-id="6716a-121">Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6716a-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="6716a-122">Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6716a-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="6716a-123">Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps oder Instanziierung von Arrayinstanzen.</span><span class="sxs-lookup"><span data-stu-id="6716a-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="6716a-124">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="6716a-125">Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="6716a-125">Indexer access</span></span>

<span data-ttu-id="6716a-126">Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6716a-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="6716a-127">Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren.</span><span class="sxs-lookup"><span data-stu-id="6716a-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="6716a-128">Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerparameter mit einem beliebigen Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="6716a-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="6716a-129">Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="6716a-130">Andere Verwendungen von „[]“</span><span class="sxs-lookup"><span data-stu-id="6716a-130">Other usages of []</span></span>

<span data-ttu-id="6716a-131">Weitere Informationen zum Zeigerelementzugriff finden Sie im Abschnitt [Zeigerelementzugriff-Operator []](pointer-related-operators.md#pointer-element-access-operator-) im Artikel [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="6716a-132">Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:</span><span class="sxs-lookup"><span data-stu-id="6716a-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="6716a-133">NULL-bedingte Operatoren „?.“</span><span class="sxs-lookup"><span data-stu-id="6716a-133">Null-conditional operators ?.</span></span> <span data-ttu-id="6716a-134">und „?[]“</span><span class="sxs-lookup"><span data-stu-id="6716a-134">and ?[]</span></span>

<span data-ttu-id="6716a-135">Ein in C# 6 und höher verfügbarer NULL-bedingter Operator wendet nur dann einen Memberzugriffsvorgang (`?.`) oder Elementzugriffsvorgang (`?[]`) auf seinen Operanden an, wenn dieser Operand als ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="6716a-135">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="6716a-136">Wenn der Operand als `null` ausgewertet wird, ist das Ergebnis der Anwendung des Operators `null`.</span><span class="sxs-lookup"><span data-stu-id="6716a-136">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="6716a-137">Der NULL-bedingte Memberzugriffsoperator `?.` wird auch als Elvis-Operator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6716a-137">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="6716a-138">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="6716a-138">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="6716a-139">D.h., wenn ein Vorgang in einer Kette von bedingten Member- oder Elementzugriffsvorgängen `null` zurückgibt, wird der Rest der Kette nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6716a-139">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="6716a-140">Im folgenden Beispiel wird `B` nicht ausgewertet, wenn `A` als `null` ausgewertet wird, und `C` wird nicht ausgewertet, wenn `A` oder `B` als `null` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="6716a-140">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="6716a-141">Im folgenden Beispiel wird die Verwendung des `?.`- und `?[]`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6716a-141">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="6716a-142">Im vorangehenden Beispiel wird auch der [NULL-Sammeloperator`??`](null-coalescing-operator.md) zum Angeben eines alternativen Ausdrucks zum Auswerten verwendet, falls das Ergebnis eines NULL-bedingten Vorgangs `null` ist.</span><span class="sxs-lookup"><span data-stu-id="6716a-142">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="6716a-143">Threadsicherer Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="6716a-143">Thread-safe delegate invocation</span></span>

<span data-ttu-id="6716a-144">Verwenden Sie den `?.`-Operator, um zu überprüfen, ob ein Delegat ungleich NULL ist, und ihn auf threadsichere Weise aufzurufen (z.B. wenn Sie [ein Ereignis auslösen](../../../standard/events/how-to-raise-and-consume-events.md)), wie der folgende Code zeigt:</span><span class="sxs-lookup"><span data-stu-id="6716a-144">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="6716a-145">Dass Code dem folgenden Code entspricht, den Sie in C# 5 oder früher verwenden würden:</span><span class="sxs-lookup"><span data-stu-id="6716a-145">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="6716a-146">Aufrufoperator „()“</span><span class="sxs-lookup"><span data-stu-id="6716a-146">Invocation operator ()</span></span>

<span data-ttu-id="6716a-147">Verwenden Sie Klammern `()` zum Aufrufen einer [Methode](../../programming-guide/classes-and-structs/methods.md), oder rufen Sie einen [Delegaten](../../programming-guide/delegates/index.md) auf.</span><span class="sxs-lookup"><span data-stu-id="6716a-147">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="6716a-148">Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6716a-148">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="6716a-149">Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit dem [ `new` ](new-operator.md)-Operator.</span><span class="sxs-lookup"><span data-stu-id="6716a-149">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="6716a-150">Andere Verwendungen von „()“</span><span class="sxs-lookup"><span data-stu-id="6716a-150">Other usages of ()</span></span>

<span data-ttu-id="6716a-151">Mit Klammern passen Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6716a-151">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="6716a-152">Weitere Informationen finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-152">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="6716a-153">[Cast-Ausdrücke](type-testing-and-cast.md#cast-operator-), die explizite Typkonvertierungen ausführen, verwenden ebenfalls Klammern.</span><span class="sxs-lookup"><span data-stu-id="6716a-153">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="6716a-154">Index vom Endeoperator ^</span><span class="sxs-lookup"><span data-stu-id="6716a-154">Index from end operator ^</span></span>

<span data-ttu-id="6716a-155">Der `^`-Operator ist in C# 8.0 und höher verfügbar und gibt die Elementposition vom Ende einer Sequenz an.</span><span class="sxs-lookup"><span data-stu-id="6716a-155">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="6716a-156">Für eine Sequenz der Länge `length` verweist `^n` auf das Element mit dem Offset `length - n` vom Beginn einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="6716a-156">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="6716a-157">`^1` zeigt beispielsweise auf das letzte Element einer Sequenz, und `^length` zeigt auf das erste Element einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="6716a-157">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="6716a-158">Wie das vorherige Beispiel zeigt, weist Ausdruck `^e` den Typ <xref:System.Index?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="6716a-158">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="6716a-159">In Ausdruck `^e` muss das Ergebnis von `e` implizit in `int` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="6716a-159">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="6716a-160">Sie können auch den `^`-Operator mit dem [Bereichsoperator](#range-operator-) verwenden, um einen Bereich von Indizes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6716a-160">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="6716a-161">Weitere Informationen finden Sie unter [Indizes und Bereiche](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-161">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="6716a-162">Bereichsoperator ..</span><span class="sxs-lookup"><span data-stu-id="6716a-162">Range operator ..</span></span>

<span data-ttu-id="6716a-163">Der Operator `..`, der in C# 8.0 und höher verfügbar ist, gibt den Anfang und das Ende eines Bereichs von Indizes als seine Operanden an.</span><span class="sxs-lookup"><span data-stu-id="6716a-163">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="6716a-164">Der linke Operand ist der *inklusive* Anfang eines Bereichs.</span><span class="sxs-lookup"><span data-stu-id="6716a-164">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="6716a-165">Der rechte Operand ist das *exklusive* Ende eines Bereichs.</span><span class="sxs-lookup"><span data-stu-id="6716a-165">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="6716a-166">Beide Operanden können ein Index vom Anfang oder vom Ende einer Sequenz sein, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="6716a-166">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="6716a-167">Wie das vorherige Beispiel zeigt, weist der Ausdruck `a..b` den Typ <xref:System.Range?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="6716a-167">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="6716a-168">In Ausdruck `a..b` muss das Ergebnis von `a` und `b` implizit in `int` oder <xref:System.Index> konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="6716a-168">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="6716a-169">Sie können Operanden des Operators `..` auslassen, um einen Bereich ohne Ende abzurufen:</span><span class="sxs-lookup"><span data-stu-id="6716a-169">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="6716a-170">`a..` entspricht `a..^0`</span><span class="sxs-lookup"><span data-stu-id="6716a-170">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="6716a-171">`..b` entspricht `0..b`</span><span class="sxs-lookup"><span data-stu-id="6716a-171">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="6716a-172">`..` entspricht `0..^0`</span><span class="sxs-lookup"><span data-stu-id="6716a-172">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="6716a-173">Weitere Informationen finden Sie unter [Indizes und Bereiche](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-173">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6716a-174">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="6716a-174">Operator overloadability</span></span>

<span data-ttu-id="6716a-175">Die Operatoren `.`, `()`, `^` und `..` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="6716a-175">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="6716a-176">Der `[]`-Operator wird auch als nicht überladbarer Operator betrachtet.</span><span class="sxs-lookup"><span data-stu-id="6716a-176">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="6716a-177">Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="6716a-177">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6716a-178">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6716a-178">C# language specification</span></span>

<span data-ttu-id="6716a-179">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="6716a-179">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="6716a-180">Member access (Memberzugriff)</span><span class="sxs-lookup"><span data-stu-id="6716a-180">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="6716a-181">Elementzugriff</span><span class="sxs-lookup"><span data-stu-id="6716a-181">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="6716a-182">NULL-bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="6716a-182">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="6716a-183">Aufrufausdrücke</span><span class="sxs-lookup"><span data-stu-id="6716a-183">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="6716a-184">Weitere Informationen zu Indizes und Bereichen finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="6716a-184">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6716a-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6716a-185">See also</span></span>

- [<span data-ttu-id="6716a-186">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6716a-186">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6716a-187">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6716a-187">C# operators</span></span>](index.md)
- [<span data-ttu-id="6716a-188">?? (NULL-Sammeloperator)</span><span class="sxs-lookup"><span data-stu-id="6716a-188">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="6716a-189">::-Operator</span><span class="sxs-lookup"><span data-stu-id="6716a-189">:: operator</span></span>](namespace-alias-qualifier.md)
