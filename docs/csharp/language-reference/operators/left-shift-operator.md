---
title: <<-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219436"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f9af7-102">\<\<-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f9af7-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="f9af7-103">Der Operator zur Linksverschiebung (`<<`) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9af7-103">The left-shift operator `<<` shifts its first operand left by the number of bits defined by its second operand.</span></span> <span data-ttu-id="f9af7-104">Alle Integertypen unterstützen den `<<` Operator.</span><span class="sxs-lookup"><span data-stu-id="f9af7-104">All integer types support the `<<` operator.</span></span> <span data-ttu-id="f9af7-105">Der Typ des zweiten Operanden muss jedoch ein [int](../keywords/int.md)-Typ oder ein Typ sein, der eine [vordefinierte implizite numerische Konvertierung](../keywords/implicit-numeric-conversions-table.md) in `int` aufweist.</span><span class="sxs-lookup"><span data-stu-id="f9af7-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="f9af7-106">Die hohen Bits, die außerhalb des Bereichs des Ergebnistyps liegen, werden verworfen, und die niedrigen leeren Bitpositionen werden auf null festgelegt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9af7-106">The high-order bits that are outside the range of the result type are discarded, and the low-order empty bit positions are set to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a><span data-ttu-id="f9af7-107">Verschiebungsanzahl</span><span class="sxs-lookup"><span data-stu-id="f9af7-107">Shift count</span></span>

<span data-ttu-id="f9af7-108">Für den Ausdruck `x << count` hängt die tatsächliche Verschiebungsanzahl folgendermaßen vom Typ von `x` ab:</span><span class="sxs-lookup"><span data-stu-id="f9af7-108">For the expression `x << count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="f9af7-109">Ist der Typ von `x` [int](../keywords/int.md) oder [uint](../keywords/uint.md), wird die Verschiebungsanzahl durch die niedrigen *fünf* Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9af7-109">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="f9af7-110">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x1F` (oder `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="f9af7-110">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="f9af7-111">Ist der Typ von `x` [long](../keywords/long.md) oder [ulong](../keywords/ulong.md), wird die Verschiebungsanzahl durch die niedrigen *sechs* Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9af7-111">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="f9af7-112">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x3F` (oder `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="f9af7-112">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="f9af7-113">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="f9af7-113">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="f9af7-114">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="f9af7-114">Remarks</span></span>

<span data-ttu-id="f9af7-115">Verschiebevorgänge verursachen niemals Überläufe und führen sowohl in [geprüften als auch in ungeprüften](../keywords/checked-and-unchecked.md) Kontexten zu identischen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="f9af7-115">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f9af7-116">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="f9af7-116">Operator overloadability</span></span>

<span data-ttu-id="f9af7-117">Benutzerdefinierte Typen können den Operator `<<` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="f9af7-117">User-defined types can [overload](../keywords/operator.md) the `<<` operator.</span></span> <span data-ttu-id="f9af7-118">Wenn ein benutzerdefinierter Typ `T` den `<<`-Operator überlädt, muss der Typ des ersten Operanden `T` und der Typ des zweiten Operanden `int` lauten.</span><span class="sxs-lookup"><span data-stu-id="f9af7-118">If a user-defined type `T` overloads the `<<` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="f9af7-119">Wenn der `<<`-Operator überladen ist, wird der [Zuweisungsoperator für die Linksverschiebung](left-shift-assignment-operator.md) `<<=` ebenfalls implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="f9af7-119">When the `<<` operator is overloaded, the [left-shift assignment operator](left-shift-assignment-operator.md) `<<=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9af7-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f9af7-120">C# language specification</span></span>

<span data-ttu-id="f9af7-121">Weitere Informationen finden Sie im Abschnitt [Verschiebungsoperatoren](~/_csharplang/spec/expressions.md#shift-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9af7-121">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9af7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9af7-122">See also</span></span>

- [<span data-ttu-id="f9af7-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f9af7-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9af7-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f9af7-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9af7-125">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f9af7-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="f9af7-126">>>-Operator</span><span class="sxs-lookup"><span data-stu-id="f9af7-126">>> operator</span></span>](right-shift-operator.md)
