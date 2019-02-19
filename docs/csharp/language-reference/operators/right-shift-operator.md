---
title: '>> -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219723"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="97281-102">>>-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="97281-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="97281-103">Der Operator zur Rechtsverschiebung (`>>`) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="97281-103">The right-shift operator `>>` shifts its first operand right by the number of bits defined by its second operand.</span></span> <span data-ttu-id="97281-104">Alle Integertypen unterstützen den `>>` Operator.</span><span class="sxs-lookup"><span data-stu-id="97281-104">All integer types support the `>>` operator.</span></span> <span data-ttu-id="97281-105">Der Typ des zweiten Operanden muss jedoch ein [int](../keywords/int.md)-Typ oder ein Typ sein, der eine [vordefinierte implizite numerische Konvertierung](../keywords/implicit-numeric-conversions-table.md) in `int` aufweist.</span><span class="sxs-lookup"><span data-stu-id="97281-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="97281-106">Beim Vorgang der Verschiebung nach rechts werden die niedrigen Bits verworfen.</span><span class="sxs-lookup"><span data-stu-id="97281-106">The right-shift operation discards the low-order bits.</span></span> <span data-ttu-id="97281-107">Die höheren leeren Bitpositionen werden basierend auf dem Typ des ersten Operanden wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="97281-107">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="97281-108">Wenn der erste Operand vom Typ [int](../keywords/int.md) oder [long](../keywords/long.md) ist, führt der Operator zur Rechtsverschiebung eine **arithmetische** Verschiebung durch: Der Wert des Bits mit dem höchsten Stellenwert (MSB, „most significant bit“) des ersten Operanden wird auf die hohen leeren Bitpositionen übertragen.</span><span class="sxs-lookup"><span data-stu-id="97281-108">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an **arithmetic** shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="97281-109">Die hohen leeren Bitpositionen werden daher auf 0 festgelegt, wenn der erste Operand nicht negativ ist, bzw. auf 1, wenn der erste Operand negativ ist.</span><span class="sxs-lookup"><span data-stu-id="97281-109">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

- <span data-ttu-id="97281-110">Wenn der erste Operand vom Typ [uint](../keywords/uint.md) oder [ulong](../keywords/ulong.md) ist, führt der Operator zur Rechtsverschiebung eine **logische** Verschiebung durch: Die hohen leeren Bitpositionen werden immer auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="97281-110">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a **logical** shift: the high-order empty bit positions are always set to zero.</span></span>

<span data-ttu-id="97281-111">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="97281-111">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a><span data-ttu-id="97281-112">Verschiebungsanzahl</span><span class="sxs-lookup"><span data-stu-id="97281-112">Shift count</span></span>

<span data-ttu-id="97281-113">Für den Ausdruck `x >> count` hängt die tatsächliche Verschiebungsanzahl folgendermaßen vom Typ von `x` ab:</span><span class="sxs-lookup"><span data-stu-id="97281-113">For the expression `x >> count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="97281-114">Ist der Typ von `x` [int](../keywords/int.md) oder [uint](../keywords/uint.md), wird die Verschiebungsanzahl durch die niedrigen *fünf* Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="97281-114">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="97281-115">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x1F` (oder `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="97281-115">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="97281-116">Ist der Typ von `x` [long](../keywords/long.md) oder [ulong](../keywords/ulong.md), wird die Verschiebungsanzahl durch die niedrigen *sechs* Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="97281-116">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="97281-117">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x3F` (oder `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="97281-117">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="97281-118">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="97281-118">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="97281-119">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="97281-119">Remarks</span></span>

<span data-ttu-id="97281-120">Verschiebevorgänge verursachen niemals Überläufe und führen sowohl in [geprüften als auch in ungeprüften](../keywords/checked-and-unchecked.md) Kontexten zu identischen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="97281-120">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="97281-121">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="97281-121">Operator overloadability</span></span>

<span data-ttu-id="97281-122">Benutzerdefinierte Typen können den Operator `>>` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="97281-122">User-defined types can [overload](../keywords/operator.md) the `>>` operator.</span></span> <span data-ttu-id="97281-123">Wenn ein benutzerdefinierter Typ `T` den `>>`-Operator überlädt, muss der Typ des ersten Operanden `T` und der Typ des zweiten Operanden `int` lauten.</span><span class="sxs-lookup"><span data-stu-id="97281-123">If a user-defined type `T` overloads the `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="97281-124">Wenn der `>>`-Operator überladen ist, wird der [Zuweisungsoperator für die Rechtsverschiebung](right-shift-assignment-operator.md) `>>=` ebenfalls implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="97281-124">When the `>>` operator is overloaded, the [right-shift assignment operator](right-shift-assignment-operator.md) `>>=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="97281-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="97281-125">C# language specification</span></span>

<span data-ttu-id="97281-126">Weitere Informationen finden Sie im Abschnitt [Verschiebungsoperatoren](~/_csharplang/spec/expressions.md#shift-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="97281-126">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97281-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97281-127">See also</span></span>

- [<span data-ttu-id="97281-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="97281-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="97281-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="97281-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="97281-130">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="97281-130">C# operators</span></span>](index.md)
- [<span data-ttu-id="97281-131"><<-Operator</span><span class="sxs-lookup"><span data-stu-id="97281-131"><< operator</span></span>](left-shift-operator.md)