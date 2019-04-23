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
ms.openlocfilehash: c03fa202b413c98230ba70ca7a0b709d7865cb91
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427382"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2ad01-102">?: Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2ad01-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="2ad01-103">Der bedingte Operator `?:`, häufig als ternärer bedingter Operator bekannt, wertet einen booleschen Ausdruck aus und gibt das Ergebnis der Auswertung von einem oder zwei Ausdrücken zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="2ad01-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="2ad01-104">Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.</span><span class="sxs-lookup"><span data-stu-id="2ad01-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="2ad01-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="2ad01-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="2ad01-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="2ad01-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="2ad01-107">Wenn `condition` `true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="2ad01-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="2ad01-108">Wenn `condition` `false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="2ad01-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="2ad01-109">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2ad01-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="2ad01-110">Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2ad01-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="2ad01-111">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="2ad01-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="2ad01-112">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="2ad01-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="2ad01-113">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2ad01-113">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="2ad01-114">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="2ad01-114">Conditional ref expression</span></span>

<span data-ttu-id="2ad01-115">Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2ad01-115">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="2ad01-116">Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ad01-116">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="2ad01-117">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="2ad01-117">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="2ad01-118">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="2ad01-118">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="2ad01-119">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2ad01-119">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="2ad01-120">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2ad01-120">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="2ad01-121">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="2ad01-121">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="2ad01-122">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2ad01-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="2ad01-123">Die Verwendung des bedingten Operators über einer [if-else](../keywords/if-else.md)-Anweisung könnte in Fällen, in denen Sie einen Wert bedingt berechnen müssen, präziseren Code zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="2ad01-123">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="2ad01-124">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="2ad01-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="2ad01-125">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="2ad01-125">Operator overloadability</span></span>

<span data-ttu-id="2ad01-126">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="2ad01-126">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2ad01-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2ad01-127">C# language specification</span></span>

<span data-ttu-id="2ad01-128">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ad01-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ad01-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ad01-129">See also</span></span>

- [<span data-ttu-id="2ad01-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2ad01-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2ad01-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2ad01-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2ad01-132">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2ad01-132">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2ad01-133">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2ad01-133">if-else statement</span></span>](../keywords/if-else.md)
- [<span data-ttu-id="2ad01-134">?.</span><span class="sxs-lookup"><span data-stu-id="2ad01-134">?.</span></span> <span data-ttu-id="2ad01-135">und ?[]-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2ad01-135">and ?[] Operators</span></span>](null-conditional-operators.md)
- [<span data-ttu-id="2ad01-136">??</span><span class="sxs-lookup"><span data-stu-id="2ad01-136">??</span></span> <span data-ttu-id="2ad01-137">Operator</span><span class="sxs-lookup"><span data-stu-id="2ad01-137">Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="2ad01-138">ref-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2ad01-138">ref keyword</span></span>](../keywords/ref.md)
