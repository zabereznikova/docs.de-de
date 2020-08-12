---
title: 'Operator „=>“: C#-Referenz'
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: b72b058c1709e7a643a70233cc3289d5d9165ca4
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916805"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="80645-102">Operator „=>-“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="80645-102">=> operator (C# reference)</span></span>

<span data-ttu-id="80645-103">Das Token `=>` wird auf zwei Weisen unterstützt: als [Lambdaoperator](#lambda-operator) und als Trennzeichen eines Membernamens und der Memberimplementierung in der [Definition eines Ausdruckskörpers](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="80645-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="80645-104">Lambdaoperator</span><span class="sxs-lookup"><span data-stu-id="80645-104">Lambda operator</span></span>

<span data-ttu-id="80645-105">In [Lambdaausdrücken](../../programming-guide/statements-expressions-operators/lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabeparameter auf der linken Seite vom Lambdakörper auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="80645-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="80645-106">Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="80645-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="80645-107">Eingabeparameter eines Lambdaausdrucks sind zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="80645-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="80645-108">Wenn der Compiler die Typen von Eingabeparametern wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen.</span><span class="sxs-lookup"><span data-stu-id="80645-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="80645-109">Wenn Sie den Typ von Eingabeparametern festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jeden Parameter festlegen:</span><span class="sxs-lookup"><span data-stu-id="80645-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="80645-110">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabeparameter definiert wird:</span><span class="sxs-lookup"><span data-stu-id="80645-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="80645-111">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="80645-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="80645-112">Ausdruckskörperdefinition</span><span class="sxs-lookup"><span data-stu-id="80645-112">Expression body definition</span></span>

<span data-ttu-id="80645-113">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="80645-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="80645-114">Dabei ist `expression` ein gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="80645-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="80645-115">Der Rückgabetyp von `expression` muss implizit in den Rückgabetyp des Members konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="80645-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="80645-116">Wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein Eigenschaften- oder Indexer-`set`-Accessor ist, muss `expression` ein [*Anweisungsausdruck*](~/_csharplang/spec/statements.md#expression-statements) sein.</span><span class="sxs-lookup"><span data-stu-id="80645-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="80645-117">Da das Ergebnis des Ausdrucks verworfen wird, kann der Rückgabetyp dieses Ausdrucks ein beliebiger Typ sein.</span><span class="sxs-lookup"><span data-stu-id="80645-117">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="80645-118">Im folgenden Beispiel wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:</span><span class="sxs-lookup"><span data-stu-id="80645-118">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="80645-119">Diese ist eine kompakte Version der folgenden Methodendefinition:</span><span class="sxs-lookup"><span data-stu-id="80645-119">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="80645-120">Ausdruckskörperdefinitionen für Methoden, Operatoren und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80645-120">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="80645-121">Ausdruckskörperdefinitionen für Konstruktoren, Finalizer sowie Eigenschaften- und Indexeraccessors werden ab C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80645-121">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="80645-122">Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="80645-122">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="80645-123">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="80645-123">Operator overloadability</span></span>

<span data-ttu-id="80645-124">Operator `=>` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="80645-124">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="80645-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="80645-125">C# language specification</span></span>

<span data-ttu-id="80645-126">Weitere Informationen zum Lambdaoperator finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="80645-126">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80645-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80645-127">See also</span></span>

- [<span data-ttu-id="80645-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="80645-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="80645-129">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="80645-129">C# operators and expressions</span></span>](index.md)
