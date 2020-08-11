---
title: Standardwertausdrücke – C#-Referenz
description: Verwenden Sie Standardwertausdrücke, um den Standardwert eines Typs abzurufen.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916862"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="e3494-103">Standardwertausdrücke (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e3494-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="e3494-104">Ein Standardwertausdruck erzeugt den [Standardwert](../builtin-types/default-values.md) für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="e3494-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="e3494-105">Es gibt zwei Arten von Standardwertausdrücken: den Aufruf des [default-Operators](#default-operator) und ein [default-Literal](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="e3494-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="e3494-106">Außerdem verwenden Sie das Schlüsselwort `default` in einer [`switch`-Anweisung](../keywords/switch.md) als case-Standardbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="e3494-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="e3494-107">default-Operator</span><span class="sxs-lookup"><span data-stu-id="e3494-107">default operator</span></span>

<span data-ttu-id="e3494-108">Das Argument für den `default`-Operator muss der Name eines Typs oder Typparameters sein, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="e3494-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="e3494-109">default-Literal</span><span class="sxs-lookup"><span data-stu-id="e3494-109">default literal</span></span>

<span data-ttu-id="e3494-110">Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="e3494-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="e3494-111">Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="e3494-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="e3494-112">Sie können das `default`-Literal in den folgenden Fälle verwenden:</span><span class="sxs-lookup"><span data-stu-id="e3494-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="e3494-113">Bei der Zuweisung oder Initialisierung einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="e3494-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="e3494-114">Bei der Deklaration des Standardwerts eines [optionalen Methodenparameters](../../methods.md#optional-parameters-and-arguments)</span><span class="sxs-lookup"><span data-stu-id="e3494-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="e3494-115">Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.</span><span class="sxs-lookup"><span data-stu-id="e3494-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="e3494-116">In einer [`return`-Anweisung](../keywords/return.md) oder als Ausdruck in einem [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)</span><span class="sxs-lookup"><span data-stu-id="e3494-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="e3494-117">Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e3494-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="e3494-118">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e3494-118">C# language specification</span></span>

<span data-ttu-id="e3494-119">Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e3494-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="e3494-120">Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="e3494-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3494-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3494-121">See also</span></span>

- [<span data-ttu-id="e3494-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e3494-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e3494-123">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e3494-123">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="e3494-124">Standardwerte der C#-Typen</span><span class="sxs-lookup"><span data-stu-id="e3494-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="e3494-125">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="e3494-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
