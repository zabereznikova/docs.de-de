---
title: /=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286519"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bf296-102">Operator /= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bf296-102">/= Operator (C# Reference)</span></span>

<span data-ttu-id="bf296-103">Der Divisionszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="bf296-103">The division assignment operator.</span></span>

<span data-ttu-id="bf296-104">Ein Ausdruck mit dem Operator `/=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="bf296-104">An expression using the `/=` operator, such as</span></span>

```csharp
x /= y
```

<span data-ttu-id="bf296-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bf296-105">is equivalent to</span></span>

```csharp
x = x / y
```

<span data-ttu-id="bf296-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="bf296-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="bf296-107">Der [Divisionsoperator](division-operator.md) `/` dividiert den ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="bf296-107">The [division operator](division-operator.md) `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="bf296-108">Er wird von allen numerischen Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf296-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="bf296-109">Im folgenden Beispiel wird die Verwendung des `/=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bf296-109">The following example demonstrates the usage of the `/=` operator:</span></span>

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="bf296-110">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="bf296-110">Operator overloadability</span></span>

<span data-ttu-id="bf296-111">Wenn ein benutzerdefinierter Typ den [Divisionsoperator](division-operator.md) `/` [überlädt](../keywords/operator.md), wird auch der Divisionszuweisungsoperator `/=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="bf296-111">If a user-defined type [overloads](../keywords/operator.md) the [division operator](division-operator.md) `/`, the division assignment operator `/=` is implicitly overloaded.</span></span> <span data-ttu-id="bf296-112">Ein benutzerdefinierter Typ kann den Divisionszuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="bf296-112">A user-defined type cannot explicitly overload the division assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bf296-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bf296-113">C# language specification</span></span>

<span data-ttu-id="bf296-114">Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf296-114">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf296-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf296-115">See also</span></span>

- [<span data-ttu-id="bf296-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bf296-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bf296-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bf296-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bf296-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="bf296-118">C# Operators</span></span>](index.md)
