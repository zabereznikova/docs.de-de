---
title: Operator += (C#-Referenz)
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192030"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9f87a-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9f87a-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="9f87a-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="9f87a-103">The addition assignment operator.</span></span>

<span data-ttu-id="9f87a-104">Ein Ausdruck mit dem Operator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="9f87a-104">An expression using the `+=` operator, such as</span></span>  

```csharp
x += y
```  

<span data-ttu-id="9f87a-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="9f87a-105">is equivalent to</span></span>  

```csharp
x = x + y
```  

<span data-ttu-id="9f87a-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9f87a-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="9f87a-107">Für numerische Typen berechnet der [Additionsoperator](addition-operator.md) `+` die Summe der Operanden.</span><span class="sxs-lookup"><span data-stu-id="9f87a-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="9f87a-108">Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der Additionsoperator die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="9f87a-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="9f87a-109">Für Delegattypen gibt der `+`-Operator eine neue Delegatinstanz zurück, die eine Kombination der Operanden ist.</span><span class="sxs-lookup"><span data-stu-id="9f87a-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="9f87a-110">Wenn ein benutzerdefinierter Typ den [Additionsoperator](addition-operator.md) `+` [überlädt](../keywords/operator.md), wird auch der Additionszuweisungsoperator `+=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="9f87a-110">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span>

<span data-ttu-id="9f87a-111">Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren.</span><span class="sxs-lookup"><span data-stu-id="9f87a-111">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="9f87a-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="9f87a-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="9f87a-113">Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9f87a-113">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a><span data-ttu-id="9f87a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f87a-114">See also</span></span>

- [<span data-ttu-id="9f87a-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9f87a-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9f87a-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9f87a-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9f87a-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9f87a-117">C# Operators</span></span>](index.md)
- [<span data-ttu-id="9f87a-118">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9f87a-118">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="9f87a-119">Delegaten</span><span class="sxs-lookup"><span data-stu-id="9f87a-119">Delegates</span></span>](../../programming-guide/delegates/index.md)
