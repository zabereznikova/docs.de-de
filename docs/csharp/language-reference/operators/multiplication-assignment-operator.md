---
title: '*=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967385"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9cb74-102">Operator \*= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9cb74-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="9cb74-103">Der Multiplikationszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="9cb74-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="9cb74-104">Ein Ausdruck mit dem Operator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="9cb74-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="9cb74-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="9cb74-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="9cb74-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9cb74-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="9cb74-107">Für numerische Typen berechnet der [\*-Operator](multiplication-operator.md) das Produkt seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="9cb74-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="9cb74-108">Im folgenden Beispiel wird die Verwendung des `*=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9cb74-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="9cb74-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="9cb74-109">Operator overloadability</span></span>

<span data-ttu-id="9cb74-110">Wenn ein benutzerdefinierter Typ den [Multiplikationsoperator](multiplication-operator.md) `*` [überlädt](../keywords/operator.md), wird auch der Multiplikationszuweisungsoperator `*=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="9cb74-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="9cb74-111">Ein benutzerdefinierter Typ kann den Multiplikationszuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="9cb74-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9cb74-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9cb74-112">C# language specification</span></span>

<span data-ttu-id="9cb74-113">Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="9cb74-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cb74-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cb74-114">See also</span></span>

- [<span data-ttu-id="9cb74-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9cb74-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9cb74-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9cb74-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9cb74-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9cb74-117">C# Operators</span></span>](index.md)
