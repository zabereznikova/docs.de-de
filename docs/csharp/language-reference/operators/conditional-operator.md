---
description: 'Operator „?:“: C#-Referenz'
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
ms.openlocfilehash: 0efa6de2b537fd3af76807938ac2b50a2716561f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122354"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6bfb2-103">Operator „?“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6bfb2-103">?: operator (C# reference)</span></span>

<span data-ttu-id="6bfb2-104">Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="6bfb2-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="6bfb2-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="6bfb2-107">Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="6bfb2-108">Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="6bfb2-109">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="6bfb2-110">Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="6bfb2-111">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="6bfb2-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="6bfb2-112">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="6bfb2-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="6bfb2-113">Sie können sich anhand der folgenden Gedächtnisstütze merken, wie der bedingte Operator ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="6bfb2-114">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="6bfb2-115">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6bfb2-115">Conditional ref expression</span></span>

<span data-ttu-id="6bfb2-116">Ab C# 7.2 kann eine lokale [ref](../keywords/ref.md#ref-locals)-Variable oder eine schreibgeschützte lokale [ref](../keywords/ref.md#ref-readonly-locals)-Variable mit dem bedingten ref-Ausdruck bedingt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-116">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="6bfb2-117">Sie können den bedingten ref-Ausdruck auch als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder als [`ref`-Methodenargument](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-117">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="6bfb2-118">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="6bfb2-119">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="6bfb2-120">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="6bfb2-121">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="6bfb2-122">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6bfb2-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="6bfb2-123">Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="6bfb2-124">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="6bfb2-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="6bfb2-125">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="6bfb2-125">Operator overloadability</span></span>

<span data-ttu-id="6bfb2-126">Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="6bfb2-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6bfb2-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6bfb2-127">C# language specification</span></span>

<span data-ttu-id="6bfb2-128">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb2-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="6bfb2-129">Weitere Informationen zum bedingten REF-Ausdruck finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb2-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bfb2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bfb2-130">See also</span></span>

- [<span data-ttu-id="6bfb2-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6bfb2-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6bfb2-132">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6bfb2-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="6bfb2-133">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6bfb2-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="6bfb2-134">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="6bfb2-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="6bfb2-135">??- und ??=-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6bfb2-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="6bfb2-136">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6bfb2-136">ref keyword</span></span>](../keywords/ref.md)
