---
title: + +=-Operatoren - und C# Verweis
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 14e62d53fca16212fae374b2627d1e96cbbca6ac
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025319"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="59c9d-102">+ und -Operatoren += (C# Verweis)</span><span class="sxs-lookup"><span data-stu-id="59c9d-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="59c9d-103">Der Operator `+` wird von den integrierten numerischen Typen, vom Typ [Zeichenfolge](../keywords/string.md) sowie von [Delegattypen](../keywords/delegate.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="59c9d-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="59c9d-104">Informationen zum arithmetischen Operator `+` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Additionsoperator +](arithmetic-operators.md#addition-operator-) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="59c9d-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="59c9d-105">Zeichenfolgenverkettung</span><span class="sxs-lookup"><span data-stu-id="59c9d-105">String concatenation</span></span>

<span data-ttu-id="59c9d-106">Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden:</span><span class="sxs-lookup"><span data-stu-id="59c9d-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="59c9d-107">Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="59c9d-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="59c9d-108">Kombinieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="59c9d-108">Delegate combination</span></span>

<span data-ttu-id="59c9d-109">Für Operanden des gleichen [Delegattyps](../keywords/delegate.md) gibt der Operator `+` eine neue Delegatinstanz zurück, die bei Aufruf den ersten Operanden und dann den zweiten Operanden aufruft.</span><span class="sxs-lookup"><span data-stu-id="59c9d-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="59c9d-110">Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist).</span><span class="sxs-lookup"><span data-stu-id="59c9d-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="59c9d-111">Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:</span><span class="sxs-lookup"><span data-stu-id="59c9d-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="59c9d-112">Um delegatentfernung auszuführen, verwenden die [ `-` Operator](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="59c9d-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="59c9d-113">Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="59c9d-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="59c9d-114">Additionszuweisungsoperator (+=)</span><span class="sxs-lookup"><span data-stu-id="59c9d-114">Addition assignment operator +=</span></span>

<span data-ttu-id="59c9d-115">Ein Ausdruck mit dem Operator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="59c9d-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="59c9d-116">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="59c9d-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="59c9d-117">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="59c9d-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="59c9d-118">Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="59c9d-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="59c9d-119">Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren.</span><span class="sxs-lookup"><span data-stu-id="59c9d-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="59c9d-120">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="59c9d-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="59c9d-121">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="59c9d-121">Operator overloadability</span></span>

<span data-ttu-id="59c9d-122">Ein benutzerdefinierter Typ kann den Operator `+` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="59c9d-122">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="59c9d-123">Wenn ein binärer Operator vom Typ `+` überladen wird, wird der Operator `+=` implizit ebenfalls überladen.</span><span class="sxs-lookup"><span data-stu-id="59c9d-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="59c9d-124">Ein benutzerdefinierter Typ kann den Operator `+=` nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="59c9d-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="59c9d-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="59c9d-125">C# language specification</span></span>

<span data-ttu-id="59c9d-126">Weitere Informationen finden Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).</span><span class="sxs-lookup"><span data-stu-id="59c9d-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="59c9d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59c9d-127">See also</span></span>

- [<span data-ttu-id="59c9d-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="59c9d-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="59c9d-129">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="59c9d-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="59c9d-130">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="59c9d-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="59c9d-131">Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Leitfaden)</span><span class="sxs-lookup"><span data-stu-id="59c9d-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="59c9d-132">Delegaten</span><span class="sxs-lookup"><span data-stu-id="59c9d-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="59c9d-133">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="59c9d-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="59c9d-134">Arithmetic operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="59c9d-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="59c9d-135">Operatoren „-“ und „-=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="59c9d-135">- and -= operators</span></span>](subtraction-operator.md)
