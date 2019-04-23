---
title: Verwenden von Nullable-Typen – C#-Programmierhandbuch
ms.custom: seodec18
description: Erfahren Sie, wie Sie mit Nullable-Typen in C# arbeiten.
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: ef7c9c18d303131b5a1c0156be820e1d475e7ec1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306650"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="3aa14-103">Verwenden von Nullable-Typen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="3aa14-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="3aa14-104">Nullable-Typen sind Typen, die alle Werte eines zugrunde liegenden `T`-Werttyps und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="3aa14-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="3aa14-105">Weitere Informationen finden Sie im Artikel [Nullable-Typen](index.md).</span><span class="sxs-lookup"><span data-stu-id="3aa14-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="3aa14-106">Sie können mit `Nullable<T>` oder `T?` auf einen Nullable-Typ verweisen.</span><span class="sxs-lookup"><span data-stu-id="3aa14-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="3aa14-107">Die beiden Formen sind austauschbar.</span><span class="sxs-lookup"><span data-stu-id="3aa14-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="3aa14-108">Deklaration und Zuweisung</span><span class="sxs-lookup"><span data-stu-id="3aa14-108">Declaration and assignment</span></span>

<span data-ttu-id="3aa14-109">Da ein Werttyp implizit in den entsprechenden Nullable-Typ konvertiert werden kann, können Sie dem Nullable-Typ genauso einen Wert zuweisen, wie Sie es auch für dessen zugrunde liegenden Werttyp tun würden.</span><span class="sxs-lookup"><span data-stu-id="3aa14-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="3aa14-110">Sie können auch den `null`-Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3aa14-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="3aa14-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3aa14-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="3aa14-112">Untersuchen des Nullable-Typwerts</span><span class="sxs-lookup"><span data-stu-id="3aa14-112">Examination of a nullable type value</span></span>

<span data-ttu-id="3aa14-113">Verwenden Sie die folgenden schreibgeschützten Eigenschaften, um eine Instanz eines Nullable-Typs für NULL zu untersuchen und einen Wert des zugrunde liegenden Typs abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3aa14-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> <span data-ttu-id="3aa14-114">gibt an, ob eine Instanz des Nullable-Typs über einen Wert des zugrunde liegenden Typs verfügt.</span><span class="sxs-lookup"><span data-stu-id="3aa14-114">indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> <span data-ttu-id="3aa14-115">ruft den Wert eines zugrunde liegenden Typs ab, wenn <xref:System.Nullable%601.HasValue%2A> gleich `true` ist.</span><span class="sxs-lookup"><span data-stu-id="3aa14-115">gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="3aa14-116">Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, löst die <xref:System.Nullable%601.Value%2A>-Eigenschaft eine <xref:System.InvalidOperationException> aus.</span><span class="sxs-lookup"><span data-stu-id="3aa14-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="3aa14-117">Im folgenden Beispielcode wird mit der `HasValue`-Eigenschaft überprüft, ob die Variable einen Wert enthält. Erst danach erfolgt die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3aa14-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="3aa14-118">Sie können eine Variable eines Nullable-Typs auch mit `null` anstelle der `HasValue`-Eigenschaft vergleichen, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="3aa14-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="3aa14-119">Ab C# 7.0 können Sie den [Musterabgleich](../../pattern-matching.md) verwenden, um einen Wert eines Nullable-Typs zu untersuchen und abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3aa14-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="3aa14-120">Konvertieren eines Nullable-Typs in einen zugrunde liegenden Typ</span><span class="sxs-lookup"><span data-stu-id="3aa14-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="3aa14-121">Wenn Sie einem Nicht-Nullable-Typ den Wert eines Nullable-Typs zuweisen müssen, verwenden Sie den [NULL-Sammeloperator`??`](../../language-reference/operators/null-coalescing-operator.md), um den Wert anzugeben, der zugewiesen werden soll, wenn ein Nullable-Typwert NULL ist (hierzu können Sie auch die <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>-Methode verwenden):</span><span class="sxs-lookup"><span data-stu-id="3aa14-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="3aa14-122">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der im Fall eines NULL-Werts des Nullable-Typs verwendet werden soll, der Standardwert des zugrunde liegenden Werttyps sein soll.</span><span class="sxs-lookup"><span data-stu-id="3aa14-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="3aa14-123">Sie können einen Nullable-Typ explizit in einen Nicht-Nullable-Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="3aa14-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="3aa14-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3aa14-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="3aa14-125">Wenn der Wert eines Nullable-Typs zur Laufzeit NULL ist, wird durch die explizite Umwandlung eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3aa14-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="3aa14-126">Ein Nicht-Nullable-Werttyp wird implizit in den entsprechenden Nullable-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3aa14-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="3aa14-127">Operatoren</span><span class="sxs-lookup"><span data-stu-id="3aa14-127">Operators</span></span>

<span data-ttu-id="3aa14-128">Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden.</span><span class="sxs-lookup"><span data-stu-id="3aa14-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="3aa14-129">Durch die Operatoren wird ein NULL-Wert erzeugt, wenn ein oder beide Operanden NULL sind. Andernfalls verwenden die Operatoren die enthaltenen Werte zur Berechnung eines Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="3aa14-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="3aa14-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3aa14-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="3aa14-131">Für den `bool?`-Typ gelten für die vordefinierten Operatoren `&` und `|` nicht die in diesem Abschnitt beschriebenen Regeln. Die Auswertung eines Operators kann auch dann einen anderen Wert als NULL ergeben, wenn einer der beiden Operanden NULL ist.</span><span class="sxs-lookup"><span data-stu-id="3aa14-131">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span> <span data-ttu-id="3aa14-132">Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3aa14-132">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="3aa14-133">Wenn bei relationalen Operatoren (`<`, `>`, `<=`, `>=`) ein oder beide Operanden NULL sind, ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="3aa14-133">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="3aa14-134">Falsch wäre die Annahme, dass im Fall des Rückgabewerts `false` für einen bestimmten Vergleich (beispielsweise `<=`) der gegenteilige Vergleich (`>`) `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3aa14-134">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="3aa14-135">Das folgende Beispiel zeigt, dass 10</span><span class="sxs-lookup"><span data-stu-id="3aa14-135">The following example shows that 10 is</span></span>

- <span data-ttu-id="3aa14-136">weder größer als oder gleich NULL</span><span class="sxs-lookup"><span data-stu-id="3aa14-136">neither greater than or equal to null,</span></span>
- <span data-ttu-id="3aa14-137">noch kleiner als NULL ist.</span><span class="sxs-lookup"><span data-stu-id="3aa14-137">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="3aa14-138">Das obige Beispiel demonstriert außerdem, dass ein Gleichheitsvergleich zweier Nullable-Typen, die beide NULL sind, `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="3aa14-138">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="3aa14-139">Weitere Informationen finden Sie im Abschnitt [Transformierte Operatoren](~/_csharplang/spec/expressions.md#lifted-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3aa14-139">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="3aa14-140">Boxing und Unboxing</span><span class="sxs-lookup"><span data-stu-id="3aa14-140">Boxing and unboxing</span></span>

<span data-ttu-id="3aa14-141">Für einen Nullable-Werttyp wird das [Boxing](../types/boxing-and-unboxing.md) entsprechend der folgenden Regeln durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="3aa14-141">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="3aa14-142">Wenn <xref:System.Nullable%601.HasValue%2A> `false` zurückgibt, wird der Nullverweis erstellt.</span><span class="sxs-lookup"><span data-stu-id="3aa14-142">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="3aa14-143">Wenn <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt, wird nicht für eine Instanz von <xref:System.Nullable%601>, sondern für einen Wert des zugrunde liegenden Werttyps `T` das Boxing durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3aa14-143">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="3aa14-144">Sie können den Werttyp, für den das Boxing durchgeführt wurde, mittels Unboxing in den entsprechenden Nullable-Typ umwandeln, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="3aa14-144">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="3aa14-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aa14-145">See also</span></span>

- [<span data-ttu-id="3aa14-146">Auf NULL festlegbare Typen</span><span class="sxs-lookup"><span data-stu-id="3aa14-146">Nullable types</span></span>](index.md)
- [<span data-ttu-id="3aa14-147">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3aa14-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3aa14-148">What exactly does 'lifted' mean? (Was bedeutet „transformiert“ genau?)</span><span class="sxs-lookup"><span data-stu-id="3aa14-148">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
