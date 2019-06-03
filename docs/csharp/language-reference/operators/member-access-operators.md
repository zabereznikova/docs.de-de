---
title: 'Operatoren für den Memberzugriff: C#-Referenz'
description: Enthält Informationen zu C#-Operatoren, die Sie für den Zugriff auf Typmember verwenden können.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
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
ms.openlocfilehash: eec70f5446eec11fa4e241b86eed4ed8d6146f85
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195779"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="bac5b-103">Operatoren für den Memberzugriff (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bac5b-103">Member access operators (C# Reference)</span></span>

<span data-ttu-id="bac5b-104">Sie können die folgenden Operatoren zum Zugriff auf einen Typmember verwenden:</span><span class="sxs-lookup"><span data-stu-id="bac5b-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="bac5b-105">[`.` (Memberzugriff)](#member-access-operator-): für den Zugriff auf einen Member eines Namespaces oder Typs</span><span class="sxs-lookup"><span data-stu-id="bac5b-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="bac5b-106">[`[]` (Zugriff auf Arrayelement oder Indexer) ](#indexer-operator-): Zugriff auf ein Arrayelement oder einen Typindexer</span><span class="sxs-lookup"><span data-stu-id="bac5b-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="bac5b-107">[`?.` und `?[]` (NULL-bedingte Operatoren)](#null-conditional-operators--and-): Ausführen eines Member- oder Elementzugriffs nur dann, wenn ein Operand ungleich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="bac5b-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="bac5b-108">[`()` (Aufruf)](#invocation-operator-): Aufrufen einer Methode, auf die zugegriffen wurde, oder Aufrufen eines Delegaten</span><span class="sxs-lookup"><span data-stu-id="bac5b-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="bac5b-109">Memberzugriffsoperator „.“</span><span class="sxs-lookup"><span data-stu-id="bac5b-109">Member access operator .</span></span>

<span data-ttu-id="bac5b-110">Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="bac5b-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="bac5b-111">Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bac5b-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="bac5b-112">Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bac5b-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="bac5b-113">Verwenden Sie eine [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.</span><span class="sxs-lookup"><span data-stu-id="bac5b-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="bac5b-114">Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bac5b-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="bac5b-115">Sie können auch `.` verwenden, um auf eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bac5b-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="bac5b-116">Indexeroperator []</span><span class="sxs-lookup"><span data-stu-id="bac5b-116">Indexer operator []</span></span>

<span data-ttu-id="bac5b-117">Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="bac5b-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="bac5b-118">Arrayzugriff</span><span class="sxs-lookup"><span data-stu-id="bac5b-118">Array access</span></span>

<span data-ttu-id="bac5b-119">Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bac5b-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="bac5b-120">Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="bac5b-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="bac5b-121">Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps oder Instanziierung von Arrayinstanzen.</span><span class="sxs-lookup"><span data-stu-id="bac5b-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="bac5b-122">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="bac5b-123">Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="bac5b-123">Indexer access</span></span>

<span data-ttu-id="bac5b-124">Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bac5b-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="bac5b-125">Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren.</span><span class="sxs-lookup"><span data-stu-id="bac5b-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="bac5b-126">Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerargumente mit einem beliebigen Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="bac5b-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="bac5b-127">Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="bac5b-128">Andere Verwendungen von „[]“</span><span class="sxs-lookup"><span data-stu-id="bac5b-128">Other usages of []</span></span>

<span data-ttu-id="bac5b-129">Weitere Informationen zum Zeigerelementzugriff finden Sie im Abschnitt [Zeigerelementzugriff-Operator []](pointer-related-operators.md#pointer-element-access-operator-) im Artikel [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="bac5b-130">Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:</span><span class="sxs-lookup"><span data-stu-id="bac5b-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="bac5b-131">NULL-bedingte Operatoren „?.“</span><span class="sxs-lookup"><span data-stu-id="bac5b-131">Null-conditional operators ?.</span></span> <span data-ttu-id="bac5b-132">und „?[]“</span><span class="sxs-lookup"><span data-stu-id="bac5b-132">and ?[]</span></span>

<span data-ttu-id="bac5b-133">Ein in C# 6 und höher verfügbarer NULL-bedingter Operator wendet nur dann einen Memberzugriffsvorgang (`?.`) oder Elementzugriffsvorgang (`?[]`) auf seinen Operanden an, wenn dieser Operand als ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="bac5b-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="bac5b-134">Wenn der Operand als `null` ausgewertet wird, ist das Ergebnis der Anwendung des Operators `null`.</span><span class="sxs-lookup"><span data-stu-id="bac5b-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="bac5b-135">Der NULL-bedingte Memberzugriffsoperator `?.` wird auch als Elvis-Operator bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bac5b-135">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="bac5b-136">Die NULL-bedingten Operatoren sind Kurzschlussoperatoren.</span><span class="sxs-lookup"><span data-stu-id="bac5b-136">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="bac5b-137">D.h., wenn ein Vorgang in einer Kette von bedingten Member- oder Elementzugriffsvorgängen `null` zurückgibt, wird der Rest der Kette nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bac5b-137">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="bac5b-138">Im folgenden Beispiel wird `B` nicht ausgewertet, wenn `A` als `null` ausgewertet wird, und `C` wird nicht ausgewertet, wenn `A` oder `B` als `null` ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="bac5b-138">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="bac5b-139">Im folgenden Beispiel wird die Verwendung des `?.`- und `?[]`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bac5b-139">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="bac5b-140">Das vorhergehende Beispiel zeigt auch die Verwendung des [NULL-Sammeloperators](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-140">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="bac5b-141">Sie könnten den NULL-Sammeloperator verwenden, um einen alternativen Ausdruck zum Auswerten in dem Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist.</span><span class="sxs-lookup"><span data-stu-id="bac5b-141">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="bac5b-142">Threadsicherer Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="bac5b-142">Thread-safe delegate invocation</span></span>

<span data-ttu-id="bac5b-143">Verwenden Sie den `?.`-Operator, um zu überprüfen, ob ein Delegat ungleich NULL ist, und ihn auf threadsichere Weise aufzurufen (z.B. wenn Sie [ein Ereignis auslösen](../../../standard/events/how-to-raise-and-consume-events.md)), wie der folgende Code zeigt:</span><span class="sxs-lookup"><span data-stu-id="bac5b-143">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="bac5b-144">Dass Code dem folgenden Code entspricht, den Sie in C# 5 oder früher verwenden würden:</span><span class="sxs-lookup"><span data-stu-id="bac5b-144">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="bac5b-145">Aufrufoperator „()“</span><span class="sxs-lookup"><span data-stu-id="bac5b-145">Invocation operator ()</span></span>

<span data-ttu-id="bac5b-146">Verwenden Sie Klammern `()` zum Aufrufen einer [Methode](../../programming-guide/classes-and-structs/methods.md), oder rufen Sie einen [Delegaten](../../programming-guide/delegates/index.md) auf.</span><span class="sxs-lookup"><span data-stu-id="bac5b-146">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="bac5b-147">Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bac5b-147">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="bac5b-148">Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit einem [ `new` ](../keywords/new-operator.md)-Operator.</span><span class="sxs-lookup"><span data-stu-id="bac5b-148">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="bac5b-149">Andere Verwendungen von „()“</span><span class="sxs-lookup"><span data-stu-id="bac5b-149">Other usages of ()</span></span>

<span data-ttu-id="bac5b-150">Mit Klammern geben Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bac5b-150">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="bac5b-151">Weitere Informationen finden Sie im Abschnitt [Hinzufügen von Klammern](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) des Artikels [Operatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-151">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="bac5b-152">Die Liste der Operatoren ist nach der Rangfolge sortiert, siehe [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="bac5b-152">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="bac5b-153">[Umwandlungsausdrücke](invocation-operator.md#cast-expression), die einen Konvertierungsoperator aufrufen, verwenden auch Klammern.</span><span class="sxs-lookup"><span data-stu-id="bac5b-153">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="bac5b-154">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="bac5b-154">Operator overloadability</span></span>

<span data-ttu-id="bac5b-155">Die Operatoren `.` und `()` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="bac5b-155">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="bac5b-156">Der `[]`-Operator wird auch als nicht überladbarer Operator betrachtet.</span><span class="sxs-lookup"><span data-stu-id="bac5b-156">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="bac5b-157">Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="bac5b-157">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bac5b-158">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bac5b-158">C# language specification</span></span>

<span data-ttu-id="bac5b-159">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bac5b-159">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bac5b-160">Member access (Memberzugriff)</span><span class="sxs-lookup"><span data-stu-id="bac5b-160">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="bac5b-161">Elementzugriff</span><span class="sxs-lookup"><span data-stu-id="bac5b-161">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="bac5b-162">NULL-bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="bac5b-162">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="bac5b-163">Aufrufausdrücke</span><span class="sxs-lookup"><span data-stu-id="bac5b-163">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="bac5b-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bac5b-164">See also</span></span>

- [<span data-ttu-id="bac5b-165">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bac5b-165">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bac5b-166">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bac5b-166">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bac5b-167">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="bac5b-167">C# Operators</span></span>](index.md)
- [<span data-ttu-id="bac5b-168">?? (NULL-Sammeloperator)</span><span class="sxs-lookup"><span data-stu-id="bac5b-168">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
