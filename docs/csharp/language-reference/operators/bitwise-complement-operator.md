---
title: ~-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 57e5baee423c0b5d9292d0ad4cbf909646eb3a38
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235718"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f213f-102">Operator ~ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f213f-102">~ Operator (C# Reference)</span></span>

<span data-ttu-id="f213f-103">Der bitweise Komplementoperator `~` ist ein unärer Operator, der ein bitweises Komplement seines Operanden erzeugt, indem jedes Bit umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="f213f-103">The bitwise complement operator `~` is a unary operator that produces a bitwise complement of its operand by reversing each bit.</span></span> <span data-ttu-id="f213f-104">Alle Integertypen unterstützen den `~` Operator.</span><span class="sxs-lookup"><span data-stu-id="f213f-104">All integer types support the `~` operator.</span></span>

> [!NOTE]
> <span data-ttu-id="f213f-105">Das `~`-Symbol wird auch für das Deklarieren von Finalizern verwendet.</span><span class="sxs-lookup"><span data-stu-id="f213f-105">The `~` symbol is also used to declare finalizers.</span></span> <span data-ttu-id="f213f-106">Weitere Informationen finden Sie unter [Finalizer](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="f213f-106">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

<span data-ttu-id="f213f-107">Im folgenden Beispiel wird die Verwendung des `~`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="f213f-107">The following example demonstrates the usage of the `~` operator:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> <span data-ttu-id="f213f-108">Im Beispiel oben werden die [in C# 7.0 eingeführten](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) und [in C# 7.2 erweiterten](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals) binären Literale verwendet.</span><span class="sxs-lookup"><span data-stu-id="f213f-108">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced  in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f213f-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="f213f-109">Operator overloadability</span></span>

<span data-ttu-id="f213f-110">Benutzerdefinierte Typen können den Operator `~` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="f213f-110">User-defined types can [overload](../keywords/operator.md) the `~` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f213f-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f213f-111">C# language specification</span></span>

<span data-ttu-id="f213f-112">Weitere Informationen finden Sie im Abschnitt [Bitweiser Komplementoperator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f213f-112">For more information, see the [Bitwise complement operator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f213f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f213f-113">See also</span></span>

- [<span data-ttu-id="f213f-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f213f-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f213f-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f213f-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f213f-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f213f-116">C# Operators</span></span>](index.md)
- [<span data-ttu-id="f213f-117">Finalizer</span><span class="sxs-lookup"><span data-stu-id="f213f-117">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="f213f-118">&-Operator</span><span class="sxs-lookup"><span data-stu-id="f213f-118">& operator</span></span>](and-operator.md)
- [<span data-ttu-id="f213f-119">|-Operator</span><span class="sxs-lookup"><span data-stu-id="f213f-119">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="f213f-120">^-Operator</span><span class="sxs-lookup"><span data-stu-id="f213f-120">^ operator</span></span>](xor-operator.md)
