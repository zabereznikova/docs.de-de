---
title: <<=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219450"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c617d-102">\<\<=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c617d-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="c617d-103">Der Linksschiebezuweisungs-Operator</span><span class="sxs-lookup"><span data-stu-id="c617d-103">The left-shift assignment operator.</span></span>

<span data-ttu-id="c617d-104">Ein Ausdruck mit dem Operator `<<=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="c617d-104">An expression using the `<<=` operator, such as</span></span>

```csharp
x <<= y
```

<span data-ttu-id="c617d-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="c617d-105">is equivalent to</span></span>

```csharp
x = x << y
```

<span data-ttu-id="c617d-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="c617d-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="c617d-107">Der [`<<`-Operator](left-shift-operator.md) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c617d-107">The [`<<` operator](left-shift-operator.md) shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="c617d-108">Im folgenden Beispiel wird die Verwendung des `<<=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c617d-108">The following example demonstrates the usage of the `<<=` operator:</span></span>

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="c617d-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="c617d-109">Operator overloadability</span></span>

<span data-ttu-id="c617d-110">Wenn ein benutzerdefinierter Typ den [`<<`-Operator](left-shift-operator.md) [überlädt](../keywords/operator.md), wird auch der Zuweisungsoperator für die Linksverschiebung (`<<=`) implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="c617d-110">If a user-defined type [overloads](../keywords/operator.md) the [`<<` operator](left-shift-operator.md), the left-shift assignment operator `<<=` is implicitly overloaded.</span></span> <span data-ttu-id="c617d-111">Ein benutzerdefinierter Typ kann den Zuweisungsoperator für die Linksverschiebung nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="c617d-111">A user-defined type cannot explicitly overload the left-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c617d-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c617d-112">C# language specification</span></span>

<span data-ttu-id="c617d-113">Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c617d-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c617d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c617d-114">See also</span></span>

- [<span data-ttu-id="c617d-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c617d-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c617d-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c617d-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c617d-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c617d-117">C# Operators</span></span>](index.md)
