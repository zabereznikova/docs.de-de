---
description: Informationen zum integrierten booleschen Typ in C#
title: 'bool-Typ: C#-Referenz'
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
- "true"
- "false"
- true_CSharpKeyword
- false_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 23e5bc34f1751b0a706c20dae340920239fcda9d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126462"
---
# <a name="bool-c-reference"></a><span data-ttu-id="6fd7a-103">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6fd7a-103">bool (C# reference)</span></span>

<span data-ttu-id="6fd7a-104">Das Schlüsselwort vom Typ `bool` ist ein Alias für den .NET-Strukturtyp <xref:System.Boolean?displayProperty=nameWithType>, der einen booleschen Wert (`true` oder `false`) darstellt.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-104">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="6fd7a-105">Um logische Operationen mit Werten vom Typ `bool` durchzuführen, verwenden Sie die [booleschen Logikoperatoren](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-105">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="6fd7a-106">Der Typ `bool` ist der Ergebnistyp von [Vergleichs](../operators/comparison-operators.md)- und [Gleichheitsoperatoren](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-106">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="6fd7a-107">Ein `bool`-Ausdruck kann ein steuernder bedingter Ausdruck in [if](../keywords/if-else.md)-, [do](../keywords/do.md)-, [while](../keywords/while.md)- und [for](../keywords/for.md)-Anweisungen und im [bedingten Operator `?:`](../operators/conditional-operator.md) sein.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-107">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="6fd7a-108">Der Standardwert des Typs `bool` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-108">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="6fd7a-109">Literale</span><span class="sxs-lookup"><span data-stu-id="6fd7a-109">Literals</span></span>

<span data-ttu-id="6fd7a-110">Sie können die Literale `true` und `false` verwenden, um eine `bool`-Variable zu initialisieren oder einen `bool`-Wert zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="6fd7a-110">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="6fd7a-111">Dreiwertige boolesche Logik</span><span class="sxs-lookup"><span data-stu-id="6fd7a-111">Three-valued Boolean logic</span></span>

<span data-ttu-id="6fd7a-112">Verwenden Sie den Nullable-Typ `bool?`, wenn Sie dreiwertige Logik unterstützen müssen (wenn Sie beispielsweise mit Datenbanken arbeiten, die einen dreiwertigen booleschen Typ unterstützen).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-112">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="6fd7a-113">Für die `bool?`-Operanden unterstützen die vordefinierten `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-113">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="6fd7a-114">Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-114">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="6fd7a-115">Weitere Informationen zu Nullable-Werttypen finden Sie unter [Nullable-Werttypen](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-115">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="6fd7a-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="6fd7a-116">Conversions</span></span>

<span data-ttu-id="6fd7a-117">C# bietet nur zwei Konvertierungen, die den Typ `bool` beinhalten.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-117">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="6fd7a-118">Dabei handelt es sich um eine implizite Konvertierung in den entsprechenden Nullable-Typ `bool?` und eine explizite Konvertierung aus dem `bool?`-Typ.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-118">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="6fd7a-119">.NET bietet jedoch zusätzliche Methoden, die Sie verwenden können, um in den oder aus dem Typ `bool` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-119">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="6fd7a-120">Weitere Informationen finden Sie im Abschnitt [Konvertieren in boolesche Werte und aus booleschen Werten](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) auf der <xref:System.Boolean?displayProperty=nameWithType>-API-Referenzseite.</span><span class="sxs-lookup"><span data-stu-id="6fd7a-120">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6fd7a-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6fd7a-121">C# language specification</span></span>

<span data-ttu-id="6fd7a-122">Weitere Informationen finden Sie im Abschnitt [Der Typ „bool“](~/_csharplang/spec/types.md#the-bool-type) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6fd7a-122">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6fd7a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fd7a-123">See also</span></span>

- [<span data-ttu-id="6fd7a-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6fd7a-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6fd7a-125">Werttypen</span><span class="sxs-lookup"><span data-stu-id="6fd7a-125">Value types</span></span>](value-types.md)
- [<span data-ttu-id="6fd7a-126">true- und false-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6fd7a-126">true and false operators</span></span>](../operators/true-false-operators.md)
