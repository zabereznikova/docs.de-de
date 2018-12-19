---
title: '&amp;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 223d2f30ee77457e1f9d5304ec299517932499d0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237024"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="e91a5-102">&amp;=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e91a5-102">&amp;= Operator (C# Reference)</span></span>

<span data-ttu-id="e91a5-103">Der AND-Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="e91a5-103">The AND assignment operator.</span></span>

<span data-ttu-id="e91a5-104">Ein Ausdruck mit dem Operator `&=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="e91a5-104">An expression using the `&=` operator, such as</span></span>

```csharp
x &= y
```

<span data-ttu-id="e91a5-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e91a5-105">is equivalent to</span></span>

```csharp
x = x & y
```

<span data-ttu-id="e91a5-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e91a5-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="e91a5-107">Für ganzzahlige Operanden berechnet der [`&`-Operator](and-operator.md) die bitweise logische AND-Operation der Operanden. Für [bool](../keywords/bool.md)-Operanden wird die logische AND-Operation der Operanden berechnet.</span><span class="sxs-lookup"><span data-stu-id="e91a5-107">For integer operands, the [`&` operator](and-operator.md) computes the bitwise logical AND of its operands; for [bool](../keywords/bool.md) operands, it computes the logical AND of its operands.</span></span>

<span data-ttu-id="e91a5-108">Im folgenden Beispiel wird die Verwendung des `&=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e91a5-108">The following example demonstrates the usage of the `&=` operator:</span></span>

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a><span data-ttu-id="e91a5-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="e91a5-109">Operator overloadability</span></span>

<span data-ttu-id="e91a5-110">Wenn ein benutzerdefinierter Typ den [`&`-Operator](and-operator.md) [überlädt](../keywords/operator.md), wird auch der AND-Zuweisungsoperator `&=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e91a5-110">If a user-defined type [overloads](../keywords/operator.md) the [`&` operator](and-operator.md), the AND assignment operator `&=` is implicitly overloaded.</span></span> <span data-ttu-id="e91a5-111">Ein benutzerdefinierter Typ kann den AND-Zuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e91a5-111">A user-defined type cannot explicitly overload the AND assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e91a5-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e91a5-112">C# language specification</span></span>

<span data-ttu-id="e91a5-113">Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e91a5-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e91a5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e91a5-114">See also</span></span>

- [<span data-ttu-id="e91a5-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e91a5-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e91a5-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e91a5-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e91a5-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e91a5-117">C# Operators</span></span>](index.md)
