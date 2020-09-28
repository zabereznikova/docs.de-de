---
description: 'Operator „?:“: C#-Referenz'
title: 'Operator „?:“: C#-Referenz'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738878"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="68417-103">Operator „?“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="68417-103">?: operator (C# reference)</span></span>

<span data-ttu-id="68417-104">Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="68417-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="68417-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="68417-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="68417-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="68417-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="68417-107">Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="68417-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="68417-108">Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="68417-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="68417-109">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="68417-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="68417-110">Ab C# 9.0 weisen bedingte Ausdrücke das Typ des Ziels auf.</span><span class="sxs-lookup"><span data-stu-id="68417-110">Beginning with C# 9.0, conditional expressions are target-typed.</span></span> <span data-ttu-id="68417-111">Wenn der Zieltyp eines bedingten Ausdrucks also bekannt ist, müssen die Typen von `consequent` und `alternative` implizit in den Zieltyp konvertierbar sein, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="68417-111">That is, if a target type of a conditional expression is known, the types of `consequent` and `alternative` must be implicitly convertible to the target type, as the following example shows:</span></span>

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

<span data-ttu-id="68417-112">Wenn der Zieltyp eines bedingten Ausdrucks nicht bekannt ist, z. B. wenn Sie das [`var`](../keywords/var.md)-Schlüsselwort nutzen oder in C# 8.0 oder älteren Versionen, muss der Typ von `consequent` und `alternative` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in den anderen geben:</span><span class="sxs-lookup"><span data-stu-id="68417-112">If a target type of a conditional expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword) or in C# 8.0 and earlier, the type of `consequent` and `alternative` must be the same or there must be an implicit conversion from one type to the other:</span></span>

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

<span data-ttu-id="68417-113">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="68417-113">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="68417-114">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="68417-114">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="68417-115">Sie können sich anhand der folgenden Gedächtnisstütze merken, wie der bedingte Operator ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="68417-115">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="68417-116">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="68417-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="68417-117">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="68417-117">Conditional ref expression</span></span>

<span data-ttu-id="68417-118">Ab C# 7.2 kann eine lokale [ref](../keywords/ref.md#ref-locals)-Variable oder eine schreibgeschützte lokale [ref](../keywords/ref.md#ref-readonly-locals)-Variable mit dem bedingten ref-Ausdruck bedingt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="68417-118">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with a conditional ref expression.</span></span> <span data-ttu-id="68417-119">Sie können einen bedingten ref-Ausdruck auch als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder als [`ref`-Methodenargument](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="68417-119">You can also use a conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="68417-120">Die Syntax für den bedingten ref-Ausdruck lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="68417-120">The syntax for a conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="68417-121">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="68417-121">Like the original conditional operator, a conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="68417-122">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="68417-122">In the case of a conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span> <span data-ttu-id="68417-123">Bedingte ref-Ausdrücke weisen nicht den Typ des Ziels auf.</span><span class="sxs-lookup"><span data-stu-id="68417-123">Conditional ref expressions are not target-typed.</span></span>

<span data-ttu-id="68417-124">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="68417-124">The following example demonstrates the usage of a conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="68417-125">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="68417-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="68417-126">Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code.</span><span class="sxs-lookup"><span data-stu-id="68417-126">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="68417-127">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="68417-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="68417-128">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="68417-128">Operator overloadability</span></span>

<span data-ttu-id="68417-129">Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="68417-129">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="68417-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="68417-130">C# language specification</span></span>

<span data-ttu-id="68417-131">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="68417-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="68417-132">Weitere Informationen zu in C# 7.2 und höher eingeführten Features finden Sie in den folgenden Featurevorschlägen:</span><span class="sxs-lookup"><span data-stu-id="68417-132">For more information about features added in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="68417-133">Bedingter ref-Ausdruck (C# 7.2)</span><span class="sxs-lookup"><span data-stu-id="68417-133">Conditional ref expressions (C# 7.2)</span></span>](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [<span data-ttu-id="68417-134">Bedingter Ausdruck mit Zieltyp (C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="68417-134">Target-typed conditional expression (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a><span data-ttu-id="68417-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68417-135">See also</span></span>

- [<span data-ttu-id="68417-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="68417-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="68417-137">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68417-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="68417-138">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="68417-138">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="68417-139">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="68417-139">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="68417-140">??- und ??=-Operatoren</span><span class="sxs-lookup"><span data-stu-id="68417-140">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="68417-141">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="68417-141">ref keyword</span></span>](../keywords/ref.md)
