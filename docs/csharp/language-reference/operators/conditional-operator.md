---
title: 'Operator „?:“: C#-Referenz'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1a17ba092d4228ba909c8774a2f7e15c2c50cfdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398214"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fa250-102">Operator „?“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fa250-102">?: operator (C# reference)</span></span>

<span data-ttu-id="fa250-103">Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="fa250-103">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="fa250-104">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="fa250-104">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="fa250-105">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="fa250-105">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="fa250-106">Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="fa250-106">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="fa250-107">Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="fa250-107">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="fa250-108">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fa250-108">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="fa250-109">Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="fa250-109">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="fa250-110">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="fa250-110">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="fa250-111">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="fa250-111">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="fa250-112">Sie können sich anhand der folgenden Gedächtnisstütze merken, wie der bedingte Operator ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="fa250-112">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="fa250-113">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fa250-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="fa250-114">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="fa250-114">Conditional ref expression</span></span>

<span data-ttu-id="fa250-115">Ab C# 7.2 kann eine lokale [ref](../keywords/ref.md#ref-locals)-Variable oder eine schreibgeschützte lokale [ref](../keywords/ref.md#ref-readonly-locals)-Variable mit dem bedingten ref-Ausdruck bedingt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fa250-115">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="fa250-116">Sie können den bedingten ref-Ausdruck auch als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder als [`ref`-Methodenargument](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa250-116">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="fa250-117">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="fa250-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="fa250-118">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="fa250-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="fa250-119">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="fa250-119">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="fa250-120">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fa250-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="fa250-121">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa250-121">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="fa250-122">Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code.</span><span class="sxs-lookup"><span data-stu-id="fa250-122">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="fa250-123">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="fa250-123">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="fa250-124">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="fa250-124">Operator overloadability</span></span>

<span data-ttu-id="fa250-125">Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="fa250-125">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fa250-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fa250-126">C# language specification</span></span>

<span data-ttu-id="fa250-127">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fa250-127">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="fa250-128">Weitere Informationen zum bedingten REF-Ausdruck finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="fa250-128">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa250-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa250-129">See also</span></span>

- [<span data-ttu-id="fa250-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fa250-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fa250-131">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="fa250-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="fa250-132">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa250-132">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="fa250-133">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="fa250-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="fa250-134">??- und ??=-Operatoren</span><span class="sxs-lookup"><span data-stu-id="fa250-134">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="fa250-135">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fa250-135">ref keyword</span></span>](../keywords/ref.md)
