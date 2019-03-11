---
title: '?: Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 210b7cabb658c6f068d9ab34c83050ad6267e426
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704907"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4d3b0-102">?: Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4d3b0-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="4d3b0-103">Der bedingte Operator `?:`, häufig als ternärer bedingter Operator bekannt, wertet einen booleschen Ausdruck aus und gibt das Ergebnis der Auswertung von einem oder zwei Ausdrücken zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="4d3b0-104">Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="4d3b0-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="4d3b0-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequence : alternative
```

<span data-ttu-id="4d3b0-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="4d3b0-107">Wenn `condition` `true` ergibt, wird der `consequence`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-107">If `condition` evaluates to `true`, the `consequence` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="4d3b0-108">Wenn `condition` `false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="4d3b0-109">Nur `consequence` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-109">Only `consequence` or `alternative` is evaluated.</span></span>

<span data-ttu-id="4d3b0-110">Der Typ von `consequence` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-110">The type of `consequence` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="4d3b0-111">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="4d3b0-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="4d3b0-112">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="4d3b0-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="4d3b0-113">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="4d3b0-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="4d3b0-114">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4d3b0-114">Conditional ref expression</span></span>

<span data-ttu-id="4d3b0-115">Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="4d3b0-116">Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="4d3b0-117">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="4d3b0-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequence : ref alternative
```

<span data-ttu-id="4d3b0-118">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequence` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequence` or `alternative`.</span></span>

<span data-ttu-id="4d3b0-119">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequence` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-119">In the case of the conditional ref expression, the type of `consequence` and `alternative` must be the same.</span></span>

<span data-ttu-id="4d3b0-120">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="4d3b0-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="4d3b0-121">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="4d3b0-121">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="4d3b0-122">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d3b0-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="4d3b0-123">Die Verwendung des bedingten Operators über einer [if-else](../keywords/if-else.md)-Anweisung könnte in Fällen, in denen Sie einen Wert bedingt berechnen müssen, präziseren Code zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="4d3b0-124">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="4d3b0-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="4d3b0-125">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="4d3b0-125">Operator overloadability</span></span>

<span data-ttu-id="4d3b0-126">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="4d3b0-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4d3b0-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d3b0-127">C# language specification</span></span>

<span data-ttu-id="4d3b0-128">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d3b0-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d3b0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d3b0-129">See also</span></span>

- [<span data-ttu-id="4d3b0-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4d3b0-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4d3b0-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4d3b0-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4d3b0-132">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="4d3b0-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="4d3b0-133">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d3b0-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="4d3b0-134">[?.- und ?[]-Operatoren](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="4d3b0-134">[?. and ?[] Operators](null-conditional-operators.md)</span></span>
- [<span data-ttu-id="4d3b0-135">?? Operator</span><span class="sxs-lookup"><span data-stu-id="4d3b0-135">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="4d3b0-136">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4d3b0-136">ref keyword</span></span>](../keywords/ref.md)
