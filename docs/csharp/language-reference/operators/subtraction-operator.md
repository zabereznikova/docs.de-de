---
title: '- und +=-Operatoren: C#-Referenz'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 7c9863134cb2a12072954bb283c7828abece3adb
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347913"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="433ae-102">Operatoren „-“ und -=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="433ae-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="433ae-103">Der Operator `-` wird von den integrierten numerischen Typen sowie von [Delegattypen](../keywords/delegate.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="433ae-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="433ae-104">Informationen zum arithmetischen Operator `-` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Subtraktionsoperator -](arithmetic-operators.md#subtraction-operator--) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="433ae-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="433ae-105">Delegatentfernung</span><span class="sxs-lookup"><span data-stu-id="433ae-105">Delegate removal</span></span>

<span data-ttu-id="433ae-106">Für Operanden des gleichen [Delegattyps](../keywords/delegate.md) gibt der Operator `-` eine wie folgt berechnete Delegatinstanz zurück:</span><span class="sxs-lookup"><span data-stu-id="433ae-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="433ae-107">Wenn beide Operanden nicht NULL sind und es sich bei der Aufrufliste des rechten Operanden um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, entsteht durch den Vorgang eine neue Aufrufliste, bei der die Einträge des rechten Operanden aus der Aufrufliste des linken Operanden entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="433ae-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="433ae-108">Wenn die Liste des rechten Operanden mehreren zusammenhängenden Unterlisten aus der Liste des linken Operanden entspricht, wird nur die äußerst rechte übereinstimmende Unterliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="433ae-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="433ae-109">Sollte durch die Entfernung eine leere Liste entstehen, ist das Ergebnis `null`.</span><span class="sxs-lookup"><span data-stu-id="433ae-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="433ae-110">Wenn es sich bei der Aufrufliste des rechten Operanden nicht um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, ist das Ergebnis des Vorgangs der linke Operand.</span><span class="sxs-lookup"><span data-stu-id="433ae-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="433ae-111">Beim Entfernen eines Delegaten, der nicht Teil des Multicastdelegaten ist, passiert nichts, und der Multicastdelegat bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="433ae-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="433ae-112">Das vorherige Beispiel veranschaulicht auch, dass Delegatinstanzen beim Entfernen von Delegaten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="433ae-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="433ae-113">Delegaten, die durch die Auswertung identischer [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md) erzeugt werden, sind beispielsweise nicht gleich.</span><span class="sxs-lookup"><span data-stu-id="433ae-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="433ae-114">Weitere Informationen über die Delegatgleichheit finden Sie in der [C#-Sprachspezifikation](../language-specification/index.md) unter [Delegieren von Gleichheitsoperatoren](~/_csharplang/spec/expressions.md#delegate-equality-operators).</span><span class="sxs-lookup"><span data-stu-id="433ae-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

- <span data-ttu-id="433ae-115">Ist der linke Operand `null`, ist das Ergebnis des Vorgangs `null`.</span><span class="sxs-lookup"><span data-stu-id="433ae-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="433ae-116">Ist der rechte Operand `null`, ist das Ergebnis des Vorgangs der linke Operand.</span><span class="sxs-lookup"><span data-stu-id="433ae-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="433ae-117">Verwenden Sie zum Kombinieren von Delegaten den [`+`-Operator](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="433ae-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="433ae-118">Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="433ae-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="433ae-119">Subtraktionszuweisungsoperator „-=“</span><span class="sxs-lookup"><span data-stu-id="433ae-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="433ae-120">Ein Ausdruck mit dem Operator `-=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="433ae-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="433ae-121">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="433ae-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="433ae-122">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="433ae-122">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="433ae-123">Im folgenden Beispiel wird die Verwendung des `-=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="433ae-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="433ae-124">Mit dem Operator `-=` können Sie auch eine Ereignishandlermethode zum Entfernen angeben, wenn Sie das Abonnement eines [Ereignisses](../keywords/event.md) kündigen.</span><span class="sxs-lookup"><span data-stu-id="433ae-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="433ae-125">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="433ae-125">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="433ae-126">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="433ae-126">Operator overloadability</span></span>

<span data-ttu-id="433ae-127">Ein benutzerdefinierter Typ kann den Operator `-` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="433ae-127">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="433ae-128">Wenn ein binärer Operator vom Typ `-` überladen wird, wird der Operator `-=` implizit ebenfalls überladen.</span><span class="sxs-lookup"><span data-stu-id="433ae-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="433ae-129">Ein benutzerdefinierter Typ kann den Operator `-=` nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="433ae-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="433ae-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="433ae-130">C# language specification</span></span>

<span data-ttu-id="433ae-131">Weitere Informationen finden Sie in den Abschnitten [Unärer Minusoperator](~/_csharplang/spec/expressions.md#unary-minus-operator) und [Subtraktionsoperator](~/_csharplang/spec/expressions.md#subtraction-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="433ae-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="433ae-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="433ae-132">See also</span></span>

- [<span data-ttu-id="433ae-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="433ae-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="433ae-134">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="433ae-134">C# operators</span></span>](index.md)
- [<span data-ttu-id="433ae-135">Delegaten</span><span class="sxs-lookup"><span data-stu-id="433ae-135">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="433ae-136">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="433ae-136">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="433ae-137">Arithmetic operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="433ae-137">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="433ae-138">Operatoren „+“ und „+=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="433ae-138">+ and += operators</span></span>](addition-operator.md)
