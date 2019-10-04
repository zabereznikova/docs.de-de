---
title: 'Verwenden von Nullable-Werttypen: C#-Programmierleitfaden'
ms.custom: seodec18
description: Erfahren Sie, wie Sie mit Nullable-Werttypen von C# arbeiten können.
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396162"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="440be-103">Verwenden von Nullable-Werttypen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="440be-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="440be-104">Nullable-Werttypen sind Typen, die alle Werte eines zugrunde liegenden `T`-Werttyps und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="440be-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="440be-105">Weitere Informationen finden Sie im Thema [Nullable-Werttypen](index.md).</span><span class="sxs-lookup"><span data-stu-id="440be-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="440be-106">C# 8.0 führt das Feature der Nullable-Verweistypen ein.</span><span class="sxs-lookup"><span data-stu-id="440be-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="440be-107">Weitere Informationen finden Sie unter [Nullable-Verweistypen](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="440be-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="440be-108">Nullable-Werttypen sind ab C# 2 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="440be-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="440be-109">Sie können auf einen Nullable-Werttyp mit einer der folgenden austauschbaren Formen verweisen: `Nullable<T>` oder `T?`.</span><span class="sxs-lookup"><span data-stu-id="440be-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="440be-110">`T` muss ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="440be-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="440be-111">Deklaration und Zuweisung</span><span class="sxs-lookup"><span data-stu-id="440be-111">Declaration and assignment</span></span>

<span data-ttu-id="440be-112">Da ein Werttyp implizit in den entsprechenden Nullable-Werttyp konvertiert werden kann, können Sie dem Nullable-Werttyp auf die gleiche Weise einen Wert zuweisen, wie es auch für dessen zugrunde liegenden Werttyp der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="440be-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="440be-113">Sie können auch den `null`-Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="440be-113">You also can assign the `null` value.</span></span> <span data-ttu-id="440be-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="440be-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="440be-115">Untersuchen des Nullable-Typwerts</span><span class="sxs-lookup"><span data-stu-id="440be-115">Examination of a nullable type value</span></span>

<span data-ttu-id="440be-116">Verwenden Sie die folgenden schreibgeschützten Eigenschaften, um eine Instanz eines Nullable-Werttyps zu untersuchen und einen Wert des zugrunde liegenden Typs abzurufen:</span><span class="sxs-lookup"><span data-stu-id="440be-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="440be-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> gibt an, ob eine Instanz des Nullable-Typs über einen Wert des zugrunde liegenden Typs verfügt.</span><span class="sxs-lookup"><span data-stu-id="440be-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="440be-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ruft den Wert eines zugrunde liegenden Typs ab, wenn <xref:System.Nullable%601.HasValue%2A> `true` ist.</span><span class="sxs-lookup"><span data-stu-id="440be-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="440be-119">Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, löst die <xref:System.Nullable%601.Value%2A>-Eigenschaft eine <xref:System.InvalidOperationException> aus.</span><span class="sxs-lookup"><span data-stu-id="440be-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="440be-120">Im folgenden Beispielcode wird mit der `HasValue`-Eigenschaft überprüft, ob die Variable einen Wert enthält. Erst danach erfolgt die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="440be-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="440be-121">Sie können eine Variable eines Nullable-Typs auch mit `null` anstelle der `HasValue`-Eigenschaft vergleichen, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="440be-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="440be-122">Ab C# 7.0 können Sie [Musterabgleich](../../pattern-matching.md) verwenden, um einen Wert eines Nullable-Werttyps zu untersuchen und abzurufen:</span><span class="sxs-lookup"><span data-stu-id="440be-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="440be-123">Konvertieren eines Nullable-Werttyps in einen zugrunde liegenden Typ</span><span class="sxs-lookup"><span data-stu-id="440be-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="440be-124">Wenn Sie einem Nicht-Nullable-Typ einen Wert eines Nullable-Werttyps zuweisen müssen, verwenden Sie den [NULL-Koaleszenzoperator `??`](../../language-reference/operators/null-coalescing-operator.md), um den zuzuordnenden Wert anzugeben, wenn ein Wert eines Nullable-Werttyps NULL ist (Sie können dazu auch die <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>-Methode verwenden):</span><span class="sxs-lookup"><span data-stu-id="440be-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="440be-125">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwendet werden soll, wenn der Wert des Nullable-Typs `null` ist, der Standardwert des zugrunde liegenden Werttyps sein soll.</span><span class="sxs-lookup"><span data-stu-id="440be-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="440be-126">Sie können einen Nullable-Werttyp explizit in einen Nicht-Nullable-Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="440be-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="440be-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="440be-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="440be-128">Wenn der Wert eines Nullable-Typs zur Laufzeit `null` ist, wird durch die explizite Umwandlung eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="440be-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="440be-129">Ein Nicht-Nullable-Werttyp wird implizit in den entsprechenden Nullable-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="440be-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="440be-130">Operatoren</span><span class="sxs-lookup"><span data-stu-id="440be-130">Operators</span></span>

<span data-ttu-id="440be-131">Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von entsprechenden Nullable-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="440be-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="440be-132">Durch die Operatoren wird ein `null` generiert, wenn mindestens ein Operand `null` ist. Andernfalls verwendet der Operator die enthaltenen Werte zur Berechnung eines Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="440be-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="440be-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="440be-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="440be-134">Für den `bool?`-Typ gelten für die vordefinierten Operatoren `&` und `|` nicht die in diesem Abschnitt beschriebenen Regeln. Die Auswertung eines Operators kann auch dann einen anderen Wert als NULL ergeben, wenn einer der beiden Operanden `null` ist.</span><span class="sxs-lookup"><span data-stu-id="440be-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="440be-135">Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="440be-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="440be-136">Wenn bei relationalen Operatoren (`<`, `>`, `<=`, `>=`) mindestens ein Operand `null` ist, ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="440be-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="440be-137">Falsch wäre die Annahme, dass im Fall des Rückgabewerts `false` für einen bestimmten Vergleich (beispielsweise `<=`) der gegenteilige Vergleich (`>`) `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="440be-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="440be-138">Das folgende Beispiel zeigt, dass 10</span><span class="sxs-lookup"><span data-stu-id="440be-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="440be-139">weder größer als oder gleich `null`</span><span class="sxs-lookup"><span data-stu-id="440be-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="440be-140">noch kleiner als `null` ist.</span><span class="sxs-lookup"><span data-stu-id="440be-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="440be-141">Das Beispiel oben demonstriert außerdem, dass ein Gleichheitsvergleich zweier Nullable-Werttypen, die beide NULL sind, `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="440be-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="440be-142">Weitere Informationen finden Sie im Abschnitt [Transformierte Operatoren](~/_csharplang/spec/expressions.md#lifted-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="440be-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="440be-143">Boxing und Unboxing</span><span class="sxs-lookup"><span data-stu-id="440be-143">Boxing and unboxing</span></span>

<span data-ttu-id="440be-144">Für einen Nullable-Werttyp wird das [Boxing](../types/boxing-and-unboxing.md) entsprechend der folgenden Regeln durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="440be-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="440be-145">Wenn <xref:System.Nullable%601.HasValue%2A> `false` zurückgibt, wird der Nullverweis erstellt.</span><span class="sxs-lookup"><span data-stu-id="440be-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="440be-146">Wenn <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt, wird nicht für eine Instanz von <xref:System.Nullable%601>, sondern für einen Wert des zugrunde liegenden Werttyps `T` das Boxing durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="440be-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="440be-147">Sie können den Werttyp, für den das Boxing durchgeführt wurde, mittels Unboxing in den entsprechenden Nullable-Typ umwandeln, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="440be-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="440be-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="440be-148">See also</span></span>

- [<span data-ttu-id="440be-149">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="440be-149">Nullable value types</span></span>](index.md)
- <span data-ttu-id="440be-150">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was bedeutet „Lifted“ genau?)</span><span class="sxs-lookup"><span data-stu-id="440be-150">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
