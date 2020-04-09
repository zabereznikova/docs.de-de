---
title: Operatoren und Ausdrücke für den Memberzugriff – C#-Referenz
description: Enthält Informationen zu C#-Operatoren, die Sie für den Zugriff auf Typmember verwenden können.
ms.date: 03/31/2020
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
ms.openlocfilehash: a132e527deadcffb4826c1965987fc09da470a09
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635305"
---
# <a name="member-access-operators-and-expressions-c-reference"></a><span data-ttu-id="ea078-103">Operatoren und Ausdrücke für den Memberzugriff (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ea078-103">Member access operators and expressions (C# reference)</span></span>

<span data-ttu-id="ea078-104">Sie können die folgenden Operatoren und Ausdrücke zum Zugriff auf einen Typmember verwenden:</span><span class="sxs-lookup"><span data-stu-id="ea078-104">You can use the following operators and expressions when you access a type member:</span></span>

- <span data-ttu-id="ea078-105">[`.` (Memberzugriff)](#member-access-expression-): für den Zugriff auf einen Member eines Namespaces oder Typs</span><span class="sxs-lookup"><span data-stu-id="ea078-105">[`.` (member access)](#member-access-expression-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="ea078-106">[`[]` (Zugriff auf Arrayelement oder Indexer) ](#indexer-operator-): Zugriff auf ein Arrayelement oder einen Typindexer</span><span class="sxs-lookup"><span data-stu-id="ea078-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="ea078-107">[`?.` und `?[]` (NULL-bedingte Operatoren)](#null-conditional-operators--and-): Ausführen eines Member- oder Elementzugriffs nur dann, wenn ein Operand ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ea078-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="ea078-108">[`()` (Aufruf)](#invocation-expression-): Aufrufen einer Methode, auf die zugegriffen wurde, oder Aufrufen eines Delegaten</span><span class="sxs-lookup"><span data-stu-id="ea078-108">[`()` (invocation)](#invocation-expression-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="ea078-109">[`^` (Index vom Ende)](#index-from-end-operator-): Angeben, dass die Elementposition vom Ende einer Sequenz erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ea078-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="ea078-110">[`..` Bereich](#range-operator-): Angeben eines Bereichs von Indizes, mit dem ein Bereich von Sequenzelementen abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea078-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-expression-"></a><span data-ttu-id="ea078-111">Memberzugriffsausdruck „.“</span><span class="sxs-lookup"><span data-stu-id="ea078-111">Member access expression .</span></span>

<span data-ttu-id="ea078-112">Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="ea078-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="ea078-113">Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="ea078-114">Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="ea078-115">Verwenden Sie eine [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.</span><span class="sxs-lookup"><span data-stu-id="ea078-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="ea078-116">Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](snippets/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="ea078-117">Sie können auch `.` verwenden, um auf eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ea078-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="ea078-118">Indexeroperator []</span><span class="sxs-lookup"><span data-stu-id="ea078-118">Indexer operator []</span></span>

<span data-ttu-id="ea078-119">Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea078-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="ea078-120">Arrayzugriff</span><span class="sxs-lookup"><span data-stu-id="ea078-120">Array access</span></span>

<span data-ttu-id="ea078-121">Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ea078-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](snippets/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="ea078-122">Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ea078-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="ea078-123">Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps oder Instanziierung von Arrayinstanzen.</span><span class="sxs-lookup"><span data-stu-id="ea078-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="ea078-124">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="ea078-125">Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="ea078-125">Indexer access</span></span>

<span data-ttu-id="ea078-126">Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ea078-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="ea078-127">Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren.</span><span class="sxs-lookup"><span data-stu-id="ea078-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="ea078-128">Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerparameter mit einem beliebigen Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ea078-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="ea078-129">Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="ea078-130">Andere Verwendungen von „[]“</span><span class="sxs-lookup"><span data-stu-id="ea078-130">Other usages of []</span></span>

<span data-ttu-id="ea078-131">Weitere Informationen zum Zeigerelementzugriff finden Sie im Abschnitt [Zeigerelementzugriff-Operator []](pointer-related-operators.md#pointer-element-access-operator-) im Artikel [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="ea078-132">Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:</span><span class="sxs-lookup"><span data-stu-id="ea078-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="ea078-133">NULL-bedingte Operatoren „?.“</span><span class="sxs-lookup"><span data-stu-id="ea078-133">Null-conditional operators ?.</span></span> <span data-ttu-id="ea078-134">und „?[]“</span><span class="sxs-lookup"><span data-stu-id="ea078-134">and ?[]</span></span>

<span data-ttu-id="ea078-135">Ein in C# 6 und höher verfügbarer NULL-bedingter Operator wendet nur dann einen [Memberzugriffsvorgang](#member-access-expression-) (`?.`) oder [Elementzugriffsvorgang](#indexer-operator-) (`?[]`) auf seinen Operanden an, wenn dieser Operand als ungleich NULL ausgewertet wird. Andernfalls gibt er `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="ea078-135">Available in C# 6 and later, a null-conditional operator applies a [member access](#member-access-expression-), `?.`, or [element access](#indexer-operator-), `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns `null`.</span></span> <span data-ttu-id="ea078-136">Dies bedeutet:</span><span class="sxs-lookup"><span data-stu-id="ea078-136">That is,</span></span>

- <span data-ttu-id="ea078-137">Wenn `a` als `null` ausgewertet wird, ist das Ergebnis von `a?.x` oder `a?[x]` `null`.</span><span class="sxs-lookup"><span data-stu-id="ea078-137">If `a` evaluates to `null`, the result of `a?.x` or `a?[x]` is `null`.</span></span>
- <span data-ttu-id="ea078-138">Wenn `a` in einen Wert ungleich NULL ausgewertet wird, ist das Ergebnis von `a?.x` oder `a?[x]` mit dem Ergebnis von `a.x` bzw. `a[x]` identisch.</span><span class="sxs-lookup"><span data-stu-id="ea078-138">If `a` evaluates to non-null, the result of `a?.x` or `a?[x]` is the same as the result of `a.x` or `a[x]`, respectively.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ea078-139">Wenn `a.x` oder `a[x]` eine Ausnahme auslöst, würden `a?.x` oder `a?[x]` für `a` ungleich NULL dieselbe Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="ea078-139">If `a.x` or `a[x]` throws an exception, `a?.x` or `a?[x]` would throw the same exception for non-null `a`.</span></span> <span data-ttu-id="ea078-140">Wenn `a` z. B. eine Arrayinstanz ungleich NULL ist und `x` außerhalb der Grenzen von `a` liegt, löst `a?[x]` eine <xref:System.IndexOutOfRangeException> aus.</span><span class="sxs-lookup"><span data-stu-id="ea078-140">For example, if `a` is a non-null array instance and `x` is outside the bounds of `a`, `a?[x]` would throw an <xref:System.IndexOutOfRangeException>.</span></span>

<span data-ttu-id="ea078-141">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="ea078-141">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="ea078-142">D.h., wenn ein Vorgang in einer Kette von bedingten Member- oder Elementzugriffsvorgängen `null` zurückgibt, wird der Rest der Kette nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea078-142">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="ea078-143">Im folgenden Beispiel wird `B` nicht ausgewertet, wenn `A` als `null` ausgewertet wird, und `C` wird nicht ausgewertet, wenn `A` oder `B` als `null` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="ea078-143">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="ea078-144">Im folgenden Beispiel wird die Verwendung des `?.`- und `?[]`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ea078-144">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="ea078-145">Im vorangehenden Beispiel wird auch der [NULL-Sammeloperator`??`](null-coalescing-operator.md) zum Angeben eines alternativen Ausdrucks zum Auswerten verwendet, falls das Ergebnis eines NULL-bedingten Vorgangs `null` ist.</span><span class="sxs-lookup"><span data-stu-id="ea078-145">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

<span data-ttu-id="ea078-146">Wenn `a.x` oder `a[x]` vom Werttyp `T` ist, der keine NULL-Werte zulässt, ist `a?.x` oder `a?[x]` vom entsprechenden [Werttyp `T?`, der keine NULL-Werte zulässt](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-146">If `a.x` or `a[x]` is of a non-nullable value type `T`, `a?.x` or `a?[x]` is of the corresponding [nullable value type](../builtin-types/nullable-value-types.md) `T?`.</span></span> <span data-ttu-id="ea078-147">Wenn Sie einen Ausdruck vom Typ `T` benötigen, wenden Sie den NULL-Sammeloperator `??` auf einen NULL-bedingten Ausdruck an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-147">If you need an expression of type `T`, apply the null-coalescing operator `??` to a null-conditional expression, as the following example shows:</span></span>

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

<span data-ttu-id="ea078-148">Wenn Sie im vorherigen Beispiel nicht den `??`-Operator verwenden und `numbers` den Wert `null` hat, wird `numbers?.Length < 2` als `false` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ea078-148">In the preceding example, if you don't use the `??` operator, `numbers?.Length < 2` evaluates to `false` when `numbers` is `null`.</span></span>

<span data-ttu-id="ea078-149">Der NULL-bedingte Memberzugriffsoperator `?.` wird auch als Elvis-Operator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ea078-149">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="ea078-150">Threadsicherer Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="ea078-150">Thread-safe delegate invocation</span></span>

<span data-ttu-id="ea078-151">Verwenden Sie den `?.`-Operator, um zu überprüfen, ob ein Delegat ungleich NULL ist, und ihn auf threadsichere Weise aufzurufen (z.B. wenn Sie [ein Ereignis auslösen](../../../standard/events/how-to-raise-and-consume-events.md)), wie der folgende Code zeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-151">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="ea078-152">Dass Code dem folgenden Code entspricht, den Sie in C# 5 oder früher verwenden würden:</span><span class="sxs-lookup"><span data-stu-id="ea078-152">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-expression-"></a><span data-ttu-id="ea078-153">Aufrufausdruck „()“</span><span class="sxs-lookup"><span data-stu-id="ea078-153">Invocation expression ()</span></span>

<span data-ttu-id="ea078-154">Verwenden Sie Klammern `()` zum Aufrufen einer [Methode](../../programming-guide/classes-and-structs/methods.md), oder rufen Sie einen [Delegaten](../../programming-guide/delegates/index.md) auf.</span><span class="sxs-lookup"><span data-stu-id="ea078-154">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="ea078-155">Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ea078-155">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="ea078-156">Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit dem [`new`](new-operator.md)-Operator.</span><span class="sxs-lookup"><span data-stu-id="ea078-156">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="ea078-157">Andere Verwendungen von „()“</span><span class="sxs-lookup"><span data-stu-id="ea078-157">Other usages of ()</span></span>

<span data-ttu-id="ea078-158">Mit Klammern passen Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea078-158">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="ea078-159">Weitere Informationen finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-159">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="ea078-160">[Cast-Ausdrücke](type-testing-and-cast.md#cast-operator-), die explizite Typkonvertierungen ausführen, verwenden ebenfalls Klammern.</span><span class="sxs-lookup"><span data-stu-id="ea078-160">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="ea078-161">Index vom Endeoperator ^</span><span class="sxs-lookup"><span data-stu-id="ea078-161">Index from end operator ^</span></span>

<span data-ttu-id="ea078-162">Der `^`-Operator ist in C# 8.0 und höher verfügbar und gibt die Elementposition vom Ende einer Sequenz an.</span><span class="sxs-lookup"><span data-stu-id="ea078-162">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="ea078-163">Für eine Sequenz der Länge `length` verweist `^n` auf das Element mit dem Offset `length - n` vom Beginn einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="ea078-163">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="ea078-164">`^1` zeigt beispielsweise auf das letzte Element einer Sequenz, und `^length` zeigt auf das erste Element einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="ea078-164">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="ea078-165">Wie das vorherige Beispiel zeigt, weist Ausdruck `^e` den Typ <xref:System.Index?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="ea078-165">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="ea078-166">In Ausdruck `^e` muss das Ergebnis von `e` implizit in `int` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="ea078-166">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="ea078-167">Sie können auch den `^`-Operator mit dem [Bereichsoperator](#range-operator-) verwenden, um einen Bereich von Indizes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea078-167">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="ea078-168">Weitere Informationen finden Sie unter [Indizes und Bereiche](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-168">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="ea078-169">Bereichsoperator .</span><span class="sxs-lookup"><span data-stu-id="ea078-169">Range operator ..</span></span>

<span data-ttu-id="ea078-170">Der Operator `..`, der in C# 8.0 und höher verfügbar ist, gibt den Anfang und das Ende eines Bereichs von Indizes als seine Operanden an.</span><span class="sxs-lookup"><span data-stu-id="ea078-170">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="ea078-171">Der linke Operand ist der *inklusive* Anfang eines Bereichs.</span><span class="sxs-lookup"><span data-stu-id="ea078-171">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="ea078-172">Der rechte Operand ist das *exklusive* Ende eines Bereichs.</span><span class="sxs-lookup"><span data-stu-id="ea078-172">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="ea078-173">Beide Operanden können ein Index vom Anfang oder vom Ende einer Sequenz sein, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="ea078-173">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="ea078-174">Wie das vorherige Beispiel zeigt, weist der Ausdruck `a..b` den Typ <xref:System.Range?displayProperty=nameWithType> auf.</span><span class="sxs-lookup"><span data-stu-id="ea078-174">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="ea078-175">In Ausdruck `a..b` muss das Ergebnis von `a` und `b` implizit in `int` oder <xref:System.Index> konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="ea078-175">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="ea078-176">Sie können Operanden des Operators `..` auslassen, um einen Bereich ohne Ende abzurufen:</span><span class="sxs-lookup"><span data-stu-id="ea078-176">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="ea078-177">`a..` entspricht `a..^0`</span><span class="sxs-lookup"><span data-stu-id="ea078-177">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="ea078-178">`..b` entspricht `0..b`</span><span class="sxs-lookup"><span data-stu-id="ea078-178">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="ea078-179">`..` entspricht `0..^0`</span><span class="sxs-lookup"><span data-stu-id="ea078-179">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="ea078-180">Weitere Informationen finden Sie unter [Indizes und Bereiche](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-180">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ea078-181">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="ea078-181">Operator overloadability</span></span>

<span data-ttu-id="ea078-182">Die Operatoren `.`, `()`, `^` und `..` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ea078-182">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="ea078-183">Der `[]`-Operator wird auch als nicht überladbarer Operator betrachtet.</span><span class="sxs-lookup"><span data-stu-id="ea078-183">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="ea078-184">Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="ea078-184">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ea078-185">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ea078-185">C# language specification</span></span>

<span data-ttu-id="ea078-186">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="ea078-186">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="ea078-187">Member access (Memberzugriff)</span><span class="sxs-lookup"><span data-stu-id="ea078-187">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="ea078-188">Elementzugriff</span><span class="sxs-lookup"><span data-stu-id="ea078-188">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="ea078-189">NULL-bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="ea078-189">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="ea078-190">Aufrufausdrücke</span><span class="sxs-lookup"><span data-stu-id="ea078-190">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="ea078-191">Weitere Informationen zu Indizes und Bereichen finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="ea078-191">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea078-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea078-192">See also</span></span>

- [<span data-ttu-id="ea078-193">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ea078-193">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ea078-194">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ea078-194">C# operators</span></span>](index.md)
- [<span data-ttu-id="ea078-195">?? (NULL-Sammeloperator)</span><span class="sxs-lookup"><span data-stu-id="ea078-195">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="ea078-196">::-Operator</span><span class="sxs-lookup"><span data-stu-id="ea078-196">:: operator</span></span>](namespace-alias-qualifier.md)
