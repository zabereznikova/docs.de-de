---
title: '- und +=-Operatoren: C#-Referenz'
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
ms.openlocfilehash: a00957c8d36a96b5ee23b9e5a309b6139b33fd36
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916684"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="9dd94-102">Operatoren „-“ und -=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9dd94-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="9dd94-103">Die Operatoren `-` und `-=` werden von den integrierten numerischen [integral](../builtin-types/integral-numeric-types.md)- und [floating-point](../builtin-types/floating-point-numeric-types.md)-Typen sowie [delegate](../builtin-types/reference-types.md#the-delegate-type)-Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9dd94-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="9dd94-104">Informationen zum arithmetischen Operator `-` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Subtraktionsoperator -](arithmetic-operators.md#subtraction-operator--) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="9dd94-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="9dd94-105">Delegatentfernung</span><span class="sxs-lookup"><span data-stu-id="9dd94-105">Delegate removal</span></span>

<span data-ttu-id="9dd94-106">Für Operanden des gleichen [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) gibt der Operator `-` eine wie folgt berechnete Delegatinstanz zurück:</span><span class="sxs-lookup"><span data-stu-id="9dd94-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="9dd94-107">Wenn beide Operanden nicht NULL sind und es sich bei der Aufrufliste des rechten Operanden um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, entsteht durch den Vorgang eine neue Aufrufliste, bei der die Einträge des rechten Operanden aus der Aufrufliste des linken Operanden entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="9dd94-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="9dd94-108">Wenn die Liste des rechten Operanden mehreren zusammenhängenden Unterlisten aus der Liste des linken Operanden entspricht, wird nur die äußerst rechte übereinstimmende Unterliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="9dd94-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="9dd94-109">Sollte durch die Entfernung eine leere Liste entstehen, ist das Ergebnis `null`.</span><span class="sxs-lookup"><span data-stu-id="9dd94-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](snippets/shared/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="9dd94-110">Wenn es sich bei der Aufrufliste des rechten Operanden nicht um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, ist das Ergebnis des Vorgangs der linke Operand.</span><span class="sxs-lookup"><span data-stu-id="9dd94-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="9dd94-111">Beim Entfernen eines Delegaten, der nicht Teil des Multicastdelegaten ist, passiert nichts, und der Multicastdelegat bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="9dd94-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](snippets/shared/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="9dd94-112">Das vorherige Beispiel veranschaulicht auch, dass Delegatinstanzen beim Entfernen von Delegaten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="9dd94-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="9dd94-113">Delegaten, die durch die Auswertung identischer [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md) erzeugt werden, sind beispielsweise nicht gleich.</span><span class="sxs-lookup"><span data-stu-id="9dd94-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="9dd94-114">Weitere Informationen über die Delegatgleichheit finden Sie in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) unter [Delegieren von Gleichheitsoperatoren](~/_csharplang/spec/expressions.md#delegate-equality-operators).</span><span class="sxs-lookup"><span data-stu-id="9dd94-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="9dd94-115">Ist der linke Operand `null`, ist das Ergebnis des Vorgangs `null`.</span><span class="sxs-lookup"><span data-stu-id="9dd94-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="9dd94-116">Ist der rechte Operand `null`, ist das Ergebnis des Vorgangs der linke Operand.</span><span class="sxs-lookup"><span data-stu-id="9dd94-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](snippets/shared/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="9dd94-117">Verwenden Sie zum Kombinieren von Delegaten den [`+`-Operator](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="9dd94-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="9dd94-118">Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dd94-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="9dd94-119">Subtraktionszuweisungsoperator „-=“</span><span class="sxs-lookup"><span data-stu-id="9dd94-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="9dd94-120">Ein Ausdruck mit dem Operator `-=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="9dd94-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="9dd94-121">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="9dd94-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="9dd94-122">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9dd94-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="9dd94-123">Im folgenden Beispiel wird die Verwendung des `-=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9dd94-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](snippets/shared/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="9dd94-124">Mit dem Operator `-=` können Sie auch eine Ereignishandlermethode zum Entfernen angeben, wenn Sie das Abonnement eines [Ereignisses](../keywords/event.md) kündigen.</span><span class="sxs-lookup"><span data-stu-id="9dd94-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="9dd94-125">Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="9dd94-125">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="9dd94-126">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="9dd94-126">Operator overloadability</span></span>

<span data-ttu-id="9dd94-127">Ein benutzerdefinierter Typ kann den Operator `-`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="9dd94-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="9dd94-128">Wenn ein binärer Operator vom Typ `-` überladen wird, wird der Operator `-=` implizit ebenfalls überladen.</span><span class="sxs-lookup"><span data-stu-id="9dd94-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="9dd94-129">Ein benutzerdefinierter Typ kann den Operator `-=` nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="9dd94-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9dd94-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9dd94-130">C# language specification</span></span>

<span data-ttu-id="9dd94-131">Weitere Informationen finden Sie in den Abschnitten [Unärer Minusoperator](~/_csharplang/spec/expressions.md#unary-minus-operator) und [Subtraktionsoperator](~/_csharplang/spec/expressions.md#subtraction-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9dd94-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dd94-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dd94-132">See also</span></span>

- [<span data-ttu-id="9dd94-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9dd94-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9dd94-134">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9dd94-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="9dd94-135">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9dd94-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="9dd94-136">Arithmetic operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="9dd94-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="9dd94-137">Operatoren „+“ und „+=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9dd94-137">+ and += operators</span></span>](addition-operator.md)
