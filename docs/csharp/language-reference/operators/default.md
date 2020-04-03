---
title: Standardwertausdrücke – C#-Referenz
description: Verwenden Sie Standardwertausdrücke, um den Standardwert eines Typs abzurufen.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 2adfd8d24066e9dad50c3c18407d3ade71b4b68e
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507177"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="a53dc-103">Standardwertausdrücke (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a53dc-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="a53dc-104">Ein Standardwertausdruck erzeugt den [Standardwert](../builtin-types/default-values.md) für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="a53dc-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="a53dc-105">Es gibt zwei Arten von Standardwertausdrücken: den Aufruf des [default-Operators](#default-operator) und ein [default-Literal](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="a53dc-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="a53dc-106">Außerdem verwenden Sie das Schlüsselwort `default` in einer [`switch`-Anweisung](../keywords/switch.md) als case-Standardbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="a53dc-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="a53dc-107">default-Operator</span><span class="sxs-lookup"><span data-stu-id="a53dc-107">default operator</span></span>

<span data-ttu-id="a53dc-108">Das Argument für den `default`-Operator muss der Name eines Typs oder Typparameters sein, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a53dc-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="a53dc-109">default-Literal</span><span class="sxs-lookup"><span data-stu-id="a53dc-109">default literal</span></span>

<span data-ttu-id="a53dc-110">Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="a53dc-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="a53dc-111">Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="a53dc-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="a53dc-112">Sie können das `default`-Literal in den folgenden Fälle verwenden:</span><span class="sxs-lookup"><span data-stu-id="a53dc-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="a53dc-113">Bei der Zuweisung oder Initialisierung einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="a53dc-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="a53dc-114">Bei der Deklaration des Standardwerts eines [optionalen Methodenparameters](../../methods.md#optional-parameters-and-arguments)</span><span class="sxs-lookup"><span data-stu-id="a53dc-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="a53dc-115">Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.</span><span class="sxs-lookup"><span data-stu-id="a53dc-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="a53dc-116">In einer [`return`-Anweisung](../keywords/return.md) oder als Ausdruck in einem [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)</span><span class="sxs-lookup"><span data-stu-id="a53dc-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="a53dc-117">Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a53dc-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="a53dc-118">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a53dc-118">C# language specification</span></span>

<span data-ttu-id="a53dc-119">Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a53dc-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a53dc-120">Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="a53dc-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a53dc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a53dc-121">See also</span></span>

- [<span data-ttu-id="a53dc-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a53dc-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a53dc-123">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a53dc-123">C# operators</span></span>](index.md)
- [<span data-ttu-id="a53dc-124">Standardwerte der C#-Typen</span><span class="sxs-lookup"><span data-stu-id="a53dc-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="a53dc-125">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="a53dc-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
