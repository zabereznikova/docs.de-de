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
ms.openlocfilehash: 82ada5e4d1f56ea93bbd7f41b04cda9f98d678c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672393"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="83974-102">?: Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="83974-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="83974-103">Der bedingte Operator `?:`, häufig als ternärer bedingter Operator bekannt, wertet einen booleschen Ausdruck aus und gibt das Ergebnis der Auswertung von einem oder zwei Ausdrücken zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="83974-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="83974-104">Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.</span><span class="sxs-lookup"><span data-stu-id="83974-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="83974-105">Die Syntax für den bedingten Operator lautet:</span><span class="sxs-lookup"><span data-stu-id="83974-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="83974-106">Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="83974-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="83974-107">Wenn `condition` `true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="83974-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="83974-108">Wenn `condition` `false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="83974-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="83974-109">Nur `consequent` oder `alternative` wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="83974-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="83974-110">Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="83974-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="83974-111">Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="83974-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="83974-112">wird wie folgt ausgewertet</span><span class="sxs-lookup"><span data-stu-id="83974-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="83974-113">Eine praktische Gedächtnisstütze für die Auswertung des Operators ist die folgende Frage:</span><span class="sxs-lookup"><span data-stu-id="83974-113">A handy mnemonic device you can use to remember how this operator evaluates is by asking:</span></span> 
```
is this condition true ? yes : no
```
<span data-ttu-id="83974-114">Dabei fungiert das ?</span><span class="sxs-lookup"><span data-stu-id="83974-114">with the ?</span></span> <span data-ttu-id="83974-115">im Operatorausdruck als Fragezeichen für die vorherige Anweisung und die daraus folgende Handlung als logische Antwort auf diese Frage.</span><span class="sxs-lookup"><span data-stu-id="83974-115">part of the operator acting as a question mark for the previous statement, and the consequent acting as the logical response to this question.</span></span>

<span data-ttu-id="83974-116">Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="83974-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="83974-117">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="83974-117">Conditional ref expression</span></span>

<span data-ttu-id="83974-118">Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="83974-118">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="83974-119">Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.</span><span class="sxs-lookup"><span data-stu-id="83974-119">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="83974-120">Die Syntax für den bedingten ref-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="83974-120">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="83974-121">Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.</span><span class="sxs-lookup"><span data-stu-id="83974-121">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="83974-122">Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="83974-122">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="83974-123">Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="83974-123">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="83974-124">Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="83974-124">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="83974-125">Bedingter Operator und eine `if..else`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="83974-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="83974-126">Die Verwendung des bedingten Operators über einer [if-else](../keywords/if-else.md)-Anweisung könnte in Fällen, in denen Sie einen Wert bedingt berechnen müssen, präziseren Code zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="83974-126">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="83974-127">Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:</span><span class="sxs-lookup"><span data-stu-id="83974-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="83974-128">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="83974-128">Operator overloadability</span></span>

<span data-ttu-id="83974-129">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="83974-129">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="83974-130">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="83974-130">C# language specification</span></span>

<span data-ttu-id="83974-131">Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Programmiersprachenspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="83974-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83974-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83974-132">See also</span></span>

- [<span data-ttu-id="83974-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="83974-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83974-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="83974-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83974-135">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="83974-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="83974-136">if-else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="83974-136">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="83974-137">[?.- und ?[]-Operatoren](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="83974-137">[?. and ?[] Operators](null-conditional-operators.md)</span></span>
- [<span data-ttu-id="83974-138">?? Operator</span><span class="sxs-lookup"><span data-stu-id="83974-138">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="83974-139">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="83974-139">ref keyword</span></span>](../keywords/ref.md)
