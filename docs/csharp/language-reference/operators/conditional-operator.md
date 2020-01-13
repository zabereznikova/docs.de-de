---
title: 'Operator „?:“: C#-Referenz'
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 60156585dd21d5d2f9c9f3916452bb8574ddd4e4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712727"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="dfcaf-102">Operator „?“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dfcaf-102">?: operator (C# reference)</span></span>

<span data-ttu-id="dfcaf-103">Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-103">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="dfcaf-104">Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="dfcaf-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="dfcaf-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="dfcaf-107">Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="dfcaf-108">Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="dfcaf-109">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="dfcaf-110">Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="dfcaf-111">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="dfcaf-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="dfcaf-112">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="dfcaf-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="dfcaf-113">Sie können sich anhand der folgenden Gedächtnisstütze merken, wie der bedingte Operator ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="dfcaf-114">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="dfcaf-115">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="dfcaf-115">Conditional ref expression</span></span>

<span data-ttu-id="dfcaf-116">Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-116">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="dfcaf-117">Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-117">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="dfcaf-118">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="dfcaf-119">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="dfcaf-120">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="dfcaf-121">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="dfcaf-122">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dfcaf-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="dfcaf-123">Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="dfcaf-124">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="dfcaf-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/csharp/language-reference/operators/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="dfcaf-125">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="dfcaf-125">Operator overloadability</span></span>

<span data-ttu-id="dfcaf-126">Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="dfcaf-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dfcaf-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="dfcaf-127">C# language specification</span></span>

<span data-ttu-id="dfcaf-128">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="dfcaf-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="dfcaf-129">Weitere Informationen zum bedingten REF-Ausdruck finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="dfcaf-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfcaf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfcaf-130">See also</span></span>

- [<span data-ttu-id="dfcaf-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dfcaf-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dfcaf-132">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="dfcaf-132">C# operators</span></span>](index.md)
- [<span data-ttu-id="dfcaf-133">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dfcaf-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="dfcaf-134">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="dfcaf-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="dfcaf-135">??- und ??=-Operatoren</span><span class="sxs-lookup"><span data-stu-id="dfcaf-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="dfcaf-136">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dfcaf-136">ref keyword</span></span>](../keywords/ref.md)
