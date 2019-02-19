---
title: '>>=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220912"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f160a-102">>>=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f160a-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="f160a-103">Der Rechtsschiebezuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="f160a-103">The right-shift assignment operator.</span></span>

<span data-ttu-id="f160a-104">Ein Ausdruck mit dem Operator `>>=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="f160a-104">An expression using the `>>=` operator, such as</span></span>

```csharp
x >>= y
```

<span data-ttu-id="f160a-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f160a-105">is equivalent to</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="f160a-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="f160a-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="f160a-107">Der [`>>`-Operator](right-shift-operator.md) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f160a-107">The [`>>` operator](right-shift-operator.md) shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="f160a-108">Im folgenden Beispiel wird die Verwendung des `>>=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="f160a-108">The following example demonstrates the usage of the `>>=` operator:</span></span>

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="f160a-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="f160a-109">Operator overloadability</span></span>

<span data-ttu-id="f160a-110">Wenn ein benutzerdefinierter Typ den [`>>`-Operator](right-shift-operator.md) [überlädt](../keywords/operator.md), wird auch der Zuweisungsoperator für die Rechtsverschiebung (`>>=`) implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="f160a-110">If a user-defined type [overloads](../keywords/operator.md) the [`>>` operator](right-shift-operator.md), the right-shift assignment operator `>>=` is implicitly overloaded.</span></span> <span data-ttu-id="f160a-111">Ein benutzerdefinierter Typ kann den Zuweisungsoperator für die Rechtsverschiebung nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="f160a-111">A user-defined type cannot explicitly overload the right-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f160a-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f160a-112">C# language specification</span></span>

<span data-ttu-id="f160a-113">Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f160a-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f160a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f160a-114">See also</span></span>

- [<span data-ttu-id="f160a-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f160a-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f160a-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f160a-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f160a-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f160a-117">C# operators</span></span>](index.md)