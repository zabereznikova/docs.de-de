---
title: 'default-Operator: C#-Referenz'
description: Verwendung des Default-Operators zum Erzeigen des Standardwerts eines Typs
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398184"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="5dc0e-103">default-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5dc0e-103">default operator (C# reference)</span></span>

<span data-ttu-id="5dc0e-104">Der `default`-Operator dient zum Erzeugen des [Standardwerts](../builtin-types/default-values.md) eines Typs.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-104">The `default` operator produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="5dc0e-105">Das Argument für den `default`-Operator muss der Name eines Typs oder ein Typparameter sein.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="5dc0e-106">Im folgenden Beispiel wird die Verwendung des `default`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5dc0e-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="5dc0e-107">Außerdem verwenden Sie das Schlüsselwort `default` in einer [`switch`-Anweisung](../keywords/switch.md) als case-Standardbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="5dc0e-108">Standardliteral</span><span class="sxs-lookup"><span data-stu-id="5dc0e-108">default literal</span></span>

<span data-ttu-id="5dc0e-109">Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="5dc0e-110">Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="5dc0e-111">Sie können das `default`-Literal in den folgenden Fälle verwenden:</span><span class="sxs-lookup"><span data-stu-id="5dc0e-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="5dc0e-112">Bei der Zuweisung oder Initialisierung einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="5dc0e-113">Bei der Deklaration des Standardwerts eines [optionalen Methodenparameters](../../methods.md#optional-parameters-and-arguments)</span><span class="sxs-lookup"><span data-stu-id="5dc0e-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="5dc0e-114">Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.</span><span class="sxs-lookup"><span data-stu-id="5dc0e-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="5dc0e-115">In einer [`return`-Anweisung](../keywords/return.md) oder als Ausdruck in einem [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)</span><span class="sxs-lookup"><span data-stu-id="5dc0e-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="5dc0e-116">Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5dc0e-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="5dc0e-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5dc0e-117">C# language specification</span></span>

<span data-ttu-id="5dc0e-118">Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5dc0e-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="5dc0e-119">Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="5dc0e-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dc0e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dc0e-120">See also</span></span>

- [<span data-ttu-id="5dc0e-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5dc0e-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5dc0e-122">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5dc0e-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="5dc0e-123">Standardwerte der C#-Typen</span><span class="sxs-lookup"><span data-stu-id="5dc0e-123">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="5dc0e-124">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="5dc0e-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
