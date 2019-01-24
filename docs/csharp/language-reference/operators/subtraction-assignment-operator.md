---
title: -=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333329"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="a6130-102">-=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a6130-102">-= operator (C# Reference)</span></span>

<span data-ttu-id="a6130-103">Der Subtraktionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="a6130-103">The subtraction assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6130-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6130-104">Remarks</span></span>

<span data-ttu-id="a6130-105">Ein Ausdruck mit dem Zuweisungsoperator `-=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="a6130-105">An expression using the `-=` assignment operator, such as</span></span>

```csharp
x -= y
```

 <span data-ttu-id="a6130-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a6130-106">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="a6130-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a6130-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="a6130-108">Die Bedeutung des [Operators -](subtraction-operator.md) hängt von den Typen `x` und `y` (Subtraktion für nummerische Operanden, Delegatentfernung für Delegatoperatoren usw.) ab.</span><span class="sxs-lookup"><span data-stu-id="a6130-108">The meaning of the [- operator](subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>

<span data-ttu-id="a6130-109">Der Operator `-=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[- Operator](subtraction-operator.md) überladen (siehe [Operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a6130-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](subtraction-operator.md) (see [operator](../keywords/operator.md)).</span></span>

<span data-ttu-id="a6130-110">Der Operator -= wird auch in C# verwendet, um ein Ereignisabonnement zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="a6130-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="a6130-111">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="a6130-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="a6130-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6130-112">Example</span></span>

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a><span data-ttu-id="a6130-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6130-113">See also</span></span>

- [<span data-ttu-id="a6130-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a6130-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a6130-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a6130-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a6130-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a6130-116">C# operators</span></span>](index.md)
