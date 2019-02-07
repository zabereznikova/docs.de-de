---
title: =>-Operator - C#-Referenz
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 0cded9d23d67e6afc8b01d6711e42759b4b51fab
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275859"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="27fd0-102">=>-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="27fd0-102">=> operator (C# Reference)</span></span>

<span data-ttu-id="27fd0-103">Das Token `=>` wird auf zwei Weisen unterstützt: als Lambdaoperator und als Trennzeichen eines Membernamens und der Memberimplementierung in der Definition eines Ausdruckskörpers.</span><span class="sxs-lookup"><span data-stu-id="27fd0-103">The `=>` token is supported in two forms: as the lambda operator and as a separator of a member name and the member implementation in an expression body definition.</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="27fd0-104">Lambdaoperator</span><span class="sxs-lookup"><span data-stu-id="27fd0-104">Lambda operator</span></span>

<span data-ttu-id="27fd0-105">In [Lambdaausdrücken](../../programming-guide/statements-expressions-operators/lambda-expressions.md) trennt der Lambdaoperator `=>` die Eingabevariablen auf der linken Seite vom Lambdakörper auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="27fd0-105">In [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md), the lambda operator `=>` separates the input variables on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="27fd0-106">Im folgenden Beispiel wird das [LINQ](../../programming-guide/concepts/linq/index.md)-Feature mit der Methodensyntax verwendet, um die Verwendung von Lambdaausdrücken zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="27fd0-106">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

<span data-ttu-id="27fd0-107">Eingabevariablen von Lambdaausdrücken sind zur Kompilierzeit stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="27fd0-107">Input variables of lambda expressions are strongly typed at compile time.</span></span> <span data-ttu-id="27fd0-108">Wenn der Compiler die Typen von Eingabevariablen wie im obigen Beispiel ableiten kann, können Sie die Typdeklarationen weglassen.</span><span class="sxs-lookup"><span data-stu-id="27fd0-108">When the compiler can infer the types of input variables, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="27fd0-109">Wenn Sie den Typ von Eingabevariablen festlegen müssen, müssen Sie ihn wie im folgenden Beispiel gezeigt für jede Variable festlegen:</span><span class="sxs-lookup"><span data-stu-id="27fd0-109">If you need to specify the type of input variables, you must do that for each variable, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

<span data-ttu-id="27fd0-110">Im folgenden Beispiel wird gezeigt, wie ein Lambdaausdruck ohne Eingabevariablen definiert wird:</span><span class="sxs-lookup"><span data-stu-id="27fd0-110">The following example shows how to define a lambda expression without input variables:</span></span>

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

<span data-ttu-id="27fd0-111">Weitere Informationen finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="27fd0-111">For more information, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="27fd0-112">Ausdruckskörperdefinition</span><span class="sxs-lookup"><span data-stu-id="27fd0-112">Expression body definition</span></span>

<span data-ttu-id="27fd0-113">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="27fd0-113">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="27fd0-114">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="27fd0-114">where *expression* is a valid expression.</span></span> <span data-ttu-id="27fd0-115">Beachten Sie, dass *expression* nur dann ein *Anweisungsausdruck* sein kann, wenn der Rückgabetyp des Members `void` ist oder der Member ein Konstruktor, Finalizer oder ein `set`-Eigenschaftenaccessor ist.</span><span class="sxs-lookup"><span data-stu-id="27fd0-115">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor, a finalizer, or a property `set` accessor.</span></span>

<span data-ttu-id="27fd0-116">Im folgenden Beispiel wird eine Ausdruckskörperdefinition für eine `Person.ToString`-Methode angegeben:</span><span class="sxs-lookup"><span data-stu-id="27fd0-116">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="27fd0-117">Diese ist eine kompakte Version der folgenden Methodendefinition:</span><span class="sxs-lookup"><span data-stu-id="27fd0-117">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="27fd0-118">Ausdruckskörperdefinitionen für Methoden und schreibgeschützte Eigenschaften werden ab C# 6 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27fd0-118">Expression body definitions for methods and read-only properties are supported starting with C# 6.</span></span> <span data-ttu-id="27fd0-119">Ausdruckskörperdefinitionen für Konstruktoren, Finalizer, Eigenschaftenaccessors und Indizes werden ab C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27fd0-119">Expression body definitions for constructors, finalizers, property accessors, and indexers are supported starting with C# 7.0.</span></span>

<span data-ttu-id="27fd0-120">Weitere Informationen finden Sie unter [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="27fd0-120">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="27fd0-121">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="27fd0-121">Operator overloadability</span></span>

<span data-ttu-id="27fd0-122">Operator `=>` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="27fd0-122">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="27fd0-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="27fd0-123">C# language specification</span></span>

<span data-ttu-id="27fd0-124">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="27fd0-124">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27fd0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27fd0-125">See also</span></span>

- [<span data-ttu-id="27fd0-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="27fd0-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27fd0-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="27fd0-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="27fd0-128">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="27fd0-128">C# Operators</span></span>](index.md)
- [<span data-ttu-id="27fd0-129">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="27fd0-129">Lambda expressions</span></span>](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="27fd0-130">Ausdruckskörpermember</span><span class="sxs-lookup"><span data-stu-id="27fd0-130">Expression-bodied members</span></span>](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)