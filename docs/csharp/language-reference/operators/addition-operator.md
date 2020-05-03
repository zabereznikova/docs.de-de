---
title: + und +=-Operatoren – C#-Referenz
ms.date: 04/23/2020
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
ms.openlocfilehash: 18364d80b8117fd4074c2c4231eac07c76829bb3
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135736"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="49282-102">Operatoren „+“ und „+=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="49282-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="49282-103">Die Operatoren `+` und `+=` werden von den integrierten numerischen [integral](../builtin-types/integral-numeric-types.md)- und [floating-point](../builtin-types/floating-point-numeric-types.md)-Typen sowie den [string](../builtin-types/reference-types.md#the-string-type)- und [delegate](../builtin-types/reference-types.md#the-delegate-type)-Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49282-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="49282-104">Informationen zum arithmetischen Operator `+` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Additionsoperator +](arithmetic-operators.md#addition-operator-) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="49282-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="49282-105">Zeichenfolgenverkettung</span><span class="sxs-lookup"><span data-stu-id="49282-105">String concatenation</span></span>

<span data-ttu-id="49282-106">Wenn ein Operand oder beide Operanden vom Typ [String](../builtin-types/reference-types.md#the-string-type) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden (die Zeichenfolgendarstellung von `null` is eine leere Zeichenfolge):</span><span class="sxs-lookup"><span data-stu-id="49282-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands (the string representation of `null` is an empty string):</span></span>

[!code-csharp-interactive[string concatenation](snippets/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="49282-107">Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="49282-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](snippets/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="49282-108">Kombinieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="49282-108">Delegate combination</span></span>

<span data-ttu-id="49282-109">Für Operanden des gleichen [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) gibt der Operator `+` eine neue Delegatinstanz zurück, die bei Aufruf den linken Operanden und dann den rechten Operanden aufruft.</span><span class="sxs-lookup"><span data-stu-id="49282-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="49282-110">Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist).</span><span class="sxs-lookup"><span data-stu-id="49282-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="49282-111">Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:</span><span class="sxs-lookup"><span data-stu-id="49282-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](snippets/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="49282-112">Um eine Delegatentfernung auszuführen, verwenden Sie den [`-`-Operator](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="49282-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="49282-113">Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="49282-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="49282-114">Additionszuweisungsoperator (+=)</span><span class="sxs-lookup"><span data-stu-id="49282-114">Addition assignment operator +=</span></span>

<span data-ttu-id="49282-115">Ein Ausdruck mit dem Operator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="49282-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="49282-116">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="49282-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="49282-117">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="49282-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="49282-118">Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="49282-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](snippets/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="49282-119">Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren.</span><span class="sxs-lookup"><span data-stu-id="49282-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="49282-120">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="49282-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="49282-121">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="49282-121">Operator overloadability</span></span>

<span data-ttu-id="49282-122">Ein benutzerdefinierter Typ kann den Operator `+`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="49282-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="49282-123">Wenn ein binärer Operator vom Typ `+` überladen wird, wird der Operator `+=` implizit ebenfalls überladen.</span><span class="sxs-lookup"><span data-stu-id="49282-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="49282-124">Ein benutzerdefinierter Typ kann den Operator `+=` nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="49282-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49282-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="49282-125">C# language specification</span></span>

<span data-ttu-id="49282-126">Weitere Informationen finden Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).</span><span class="sxs-lookup"><span data-stu-id="49282-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49282-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49282-127">See also</span></span>

- [<span data-ttu-id="49282-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="49282-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="49282-129">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="49282-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="49282-130">Verketten mehrerer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="49282-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="49282-131">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="49282-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="49282-132">Arithmetic operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="49282-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="49282-133">Operatoren „-“ und „-=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="49282-133">- and -= operators</span></span>](subtraction-operator.md)
