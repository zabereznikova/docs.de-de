---
title: Operator += (C#-Referenz)
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ac9330e283cb58ae4e0ee7b644aa2c22bdf64c46
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192030"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="84140-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="84140-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="84140-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="84140-103">The addition assignment operator.</span></span>

<span data-ttu-id="84140-104">Ein Ausdruck mit dem Operator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="84140-104">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="84140-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="84140-105">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="84140-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="84140-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="84140-107">Für numerische Typen berechnet der [Additionsoperator](addition-operator.md) `+` die Summe der Operanden.</span><span class="sxs-lookup"><span data-stu-id="84140-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="84140-108">Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der Additionsoperator die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="84140-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="84140-109">Für Delegattypen gibt der `+`-Operator eine neue Delegatinstanz zurück, die eine Kombination der Operanden ist.</span><span class="sxs-lookup"><span data-stu-id="84140-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="84140-110">Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren.</span><span class="sxs-lookup"><span data-stu-id="84140-110">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="84140-111">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="84140-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="84140-112">Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="84140-112">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="84140-113">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="84140-113">Operator overloadability</span></span>

<span data-ttu-id="84140-114">Wenn ein benutzerdefinierter Typ den [Additionsoperator](addition-operator.md) `+` [überlädt](../keywords/operator.md), wird auch der Additionszuweisungsoperator `+=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="84140-114">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span> <span data-ttu-id="84140-115">Ein benutzerdefinierter Typ kann den Additionszuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="84140-115">A user-defined type cannot explicitly overload the addition assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="84140-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="84140-116">C# language specification</span></span>

<span data-ttu-id="84140-117">Weitere Informationen finden Sie in den Abschnitten [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) und [Ereigniszuweisung](~/_csharplang/spec/expressions.md#event-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="84140-117">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) and [Event assignment](~/_csharplang/spec/expressions.md#event-assignment) sections of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84140-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84140-118">See also</span></span>

- [<span data-ttu-id="84140-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="84140-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="84140-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="84140-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="84140-121">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="84140-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="84140-122">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="84140-122">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="84140-123">Delegaten</span><span class="sxs-lookup"><span data-stu-id="84140-123">Delegates</span></span>](../../programming-guide/delegates/index.md)
