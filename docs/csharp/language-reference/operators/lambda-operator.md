---
title: 'Operator „=>“: C#-Referenz'
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 61cc3c3ab4f0b22c4040a9b8a025c81071f4d942
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712701"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="18609-102">Operator „=>-“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="18609-102">=> operator (C# reference)</span></span>

<span data-ttu-id="18609-103">Das Token `=>` wird auf zwei Weisen unterstützt: als [Lambdaoperator](#lambda-operator) und als Trennzeichen eines Membernamens und der Memberimplementierung in der [Definition eines Ausdruckskörpers](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="18609-103">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="18609-104">Lambdaoperator</span><span class="sxs-lookup"><span data-stu-id="18609-104">Lambda operator</span></span>

<span data-ttu-id="18609-105">In [Lambdaausdrücken](../../programming-guide/statements-expressions-operators/lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabeparameter auf der linken Seite vom Lambdakörper auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="18609-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="18609-106">Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="18609-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="18609-107">Eingabeparameter eines Lambdaausdrucks sind zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="18609-107">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="18609-108">Wenn der Compiler die Typen von Eingabeparametern wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen.</span><span class="sxs-lookup"><span data-stu-id="18609-108">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="18609-109">Wenn Sie den Typ von Eingabeparametern festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jeden Parameter festlegen:</span><span class="sxs-lookup"><span data-stu-id="18609-109">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="18609-110">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabeparameter definiert wird:</span><span class="sxs-lookup"><span data-stu-id="18609-110">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](~/samples/csharp/language-reference/operators/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="18609-111">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="18609-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="18609-112">Ausdruckskörperdefinition</span><span class="sxs-lookup"><span data-stu-id="18609-112">Expression body definition</span></span>

<span data-ttu-id="18609-113">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="18609-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="18609-114">Dabei ist `expression` ein gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="18609-114">where `expression` is a valid expression.</span></span> <span data-ttu-id="18609-115">Der Rückgabetyp von `expression` muss implizit in den Rückgabetyp des Members konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="18609-115">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="18609-116">Wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein `set`-Eigenschaftenaccessor ist, muss `expression` ein [ *-Anweisungsausdruck*](~/_csharplang/spec/statements.md#expression-statements) sein, der dann einen beliebigen Typ aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="18609-116">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements), which can be of any type.</span></span>

<span data-ttu-id="18609-117">Im folgenden Beispiel wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:</span><span class="sxs-lookup"><span data-stu-id="18609-117">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="18609-118">Diese ist eine kompakte Version der folgenden Methodendefinition:</span><span class="sxs-lookup"><span data-stu-id="18609-118">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="18609-119">Ausdruckskörperdefinitionen für Methoden, Operatoren und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18609-119">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="18609-120">Ausdruckskörperdefinitionen für Konstruktoren, Finalizer sowie Eigenschaften- und Indexeraccessors werden ab C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18609-120">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="18609-121">Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="18609-121">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="18609-122">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="18609-122">Operator overloadability</span></span>

<span data-ttu-id="18609-123">Operator `=>` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="18609-123">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18609-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="18609-124">C# language specification</span></span>

<span data-ttu-id="18609-125">Weitere Informationen zum Lambdaoperator finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="18609-125">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18609-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18609-126">See also</span></span>

- [<span data-ttu-id="18609-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="18609-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="18609-128">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="18609-128">C# operators</span></span>](index.md)
