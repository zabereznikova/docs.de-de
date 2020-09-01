---
description: 'Operator „=>“: C#-Referenz'
title: 'Operator „=>“: C#-Referenz'
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6a4df3a4bd358b87f98ff1bd5a3f624b1029a73b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128360"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e64f5-103">Operator „=>-“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e64f5-103">=> operator (C# reference)</span></span>

<span data-ttu-id="e64f5-104">Das Token `=>` wird auf zwei Weisen unterstützt: als [Lambdaoperator](#lambda-operator) und als Trennzeichen eines Membernamens und der Memberimplementierung in der [Definition eines Ausdruckskörpers](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="e64f5-104">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="e64f5-105">Lambdaoperator</span><span class="sxs-lookup"><span data-stu-id="e64f5-105">Lambda operator</span></span>

<span data-ttu-id="e64f5-106">In [Lambdaausdrücken](lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabeparameter auf der linken Seite vom Lambdakörper auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="e64f5-106">In [lambda expressions](lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="e64f5-107">Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="e64f5-107">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="e64f5-108">Eingabeparameter eines Lambdaausdrucks sind zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="e64f5-108">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="e64f5-109">Wenn der Compiler die Typen von Eingabeparametern wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen.</span><span class="sxs-lookup"><span data-stu-id="e64f5-109">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="e64f5-110">Wenn Sie den Typ von Eingabeparametern festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jeden Parameter festlegen:</span><span class="sxs-lookup"><span data-stu-id="e64f5-110">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="e64f5-111">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabeparameter definiert wird:</span><span class="sxs-lookup"><span data-stu-id="e64f5-111">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="e64f5-112">Weitere Informationen finden Sie unter [Lambdaausdrücke](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e64f5-112">For more information, see [Lambda expressions](lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="e64f5-113">Ausdruckskörperdefinition</span><span class="sxs-lookup"><span data-stu-id="e64f5-113">Expression body definition</span></span>

<span data-ttu-id="e64f5-114">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="e64f5-114">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="e64f5-115">Dabei ist `expression` ein gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e64f5-115">where `expression` is a valid expression.</span></span> <span data-ttu-id="e64f5-116">Der Rückgabetyp von `expression` muss implizit in den Rückgabetyp des Members konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e64f5-116">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="e64f5-117">Wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein Eigenschaften- oder Indexer-`set`-Accessor ist, muss `expression` ein [*Anweisungsausdruck*](~/_csharplang/spec/statements.md#expression-statements) sein.</span><span class="sxs-lookup"><span data-stu-id="e64f5-117">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="e64f5-118">Da das Ergebnis des Ausdrucks verworfen wird, kann der Rückgabetyp dieses Ausdrucks ein beliebiger Typ sein.</span><span class="sxs-lookup"><span data-stu-id="e64f5-118">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="e64f5-119">Im folgenden Beispiel wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:</span><span class="sxs-lookup"><span data-stu-id="e64f5-119">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="e64f5-120">Diese ist eine kompakte Version der folgenden Methodendefinition:</span><span class="sxs-lookup"><span data-stu-id="e64f5-120">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="e64f5-121">Ausdruckskörperdefinitionen für Methoden, Operatoren und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e64f5-121">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="e64f5-122">Ausdruckskörperdefinitionen für Konstruktoren, Finalizer sowie Eigenschaften- und Indexeraccessors werden ab C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e64f5-122">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="e64f5-123">Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="e64f5-123">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="e64f5-124">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="e64f5-124">Operator overloadability</span></span>

<span data-ttu-id="e64f5-125">Operator `=>` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="e64f5-125">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e64f5-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e64f5-126">C# language specification</span></span>

<span data-ttu-id="e64f5-127">Weitere Informationen zum Lambdaoperator finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e64f5-127">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e64f5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e64f5-128">See also</span></span>

- [<span data-ttu-id="e64f5-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e64f5-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e64f5-130">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e64f5-130">C# operators and expressions</span></span>](index.md)
