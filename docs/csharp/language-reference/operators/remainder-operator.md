---
title: '%-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: a5c12b6683e35cc1ec2d40446dd0ed068c3d2552
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236478"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="07fd3-102">%-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="07fd3-102">% Operator (C# Reference)</span></span>

<span data-ttu-id="07fd3-103">Der Restoperator `%` berechnet den Rest nach der Division seines ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="07fd3-103">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

<span data-ttu-id="07fd3-104">Benutzerdefinierte Typen können den Operator `%` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="07fd3-104">User-defined types can [overload](../keywords/operator.md) the `%` operator.</span></span> <span data-ttu-id="07fd3-105">Wenn `%` überladen ist, ist der [Restzuweisungsoperator](remainder-assignment-operator.md) `%=` ebenfalls implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="07fd3-105">When the `%` is overloaded, the [remainder assignment operator](remainder-assignment-operator.md) `%=` is also implicitly overloaded.</span></span>

<span data-ttu-id="07fd3-106">Alle numerischen Typen unterstützen den Restoperator.</span><span class="sxs-lookup"><span data-stu-id="07fd3-106">All numeric types support the remainder operator.</span></span>

## <a name="integer-remainder"></a><span data-ttu-id="07fd3-107">Ganzzahliger Rest</span><span class="sxs-lookup"><span data-stu-id="07fd3-107">Integer remainder</span></span>
  
<span data-ttu-id="07fd3-108">Für ganzzahlige Operanden entspricht das Ergebnis von `a % b` dem von `a - (a / b) * b` erzeugten Wert.</span><span class="sxs-lookup"><span data-stu-id="07fd3-108">For the integer operands, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="07fd3-109">Das Vorzeichen des Rests, der ungleich 0 (null) ist, ist wie im folgenden Beispiel gezeigt identisch mit dem des ersten Operanden:</span><span class="sxs-lookup"><span data-stu-id="07fd3-109">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a><span data-ttu-id="07fd3-110">Gleitkommarest</span><span class="sxs-lookup"><span data-stu-id="07fd3-110">Floating-point remainder</span></span>

<span data-ttu-id="07fd3-111">Für die Operanden [float](../keywords/float.md) und [double](../keywords/double.md) entspricht das Ergebnis von `x % y` für die begrenzten Werte `x` und `y` dem Wert `z`, sodass:</span><span class="sxs-lookup"><span data-stu-id="07fd3-111">For the [float](../keywords/float.md) and [double](../keywords/double.md) operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="07fd3-112">das Vorzeichen von `z` dem Vorzeichen von `x` entspricht, sofern der Wert nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="07fd3-112">the sign of `z`, if non-zero, is the same as the sign of `x`;</span></span>
- <span data-ttu-id="07fd3-113">der absolute Wert von `z` dem von `|x| - n * |y|` erzeugten Wert entspricht, wobei `n` der größten möglichen Ganzzahl entspricht, die kleiner oder gleich `|x| / |y|` ist. Dementsprechend sind `|x|` und `|y|` jeweils die absoluten Werte von `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="07fd3-113">the absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

<span data-ttu-id="07fd3-114">Weitere Informationen zum Verhalten des `%`-Operators bei nicht begrenzten Operanden finden Sie im Abschnitt [Restoperator](~/_csharplang/spec/expressions.md#remainder-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="07fd3-114">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="07fd3-115">Diese Methode zum Berechnen des Rests ist analog zu der Methode, die für ganzzahlige Operanden verwendet wird, unterscheidet sich jedoch von der Norm IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="07fd3-115">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="07fd3-116">Wenn Sie den Restvorgang benötigen, der der Norm IEEE 754 entspricht, verwenden Sie die Methode <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="07fd3-116">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="07fd3-117">Im folgenden Beispiel wird das Verhalten des Restoperators für die Operanden `float` und `double` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="07fd3-117">The following example demonstrates the behavior of the remainder operator for `float` and `double` operands:</span></span>

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

<span data-ttu-id="07fd3-118">Beachten Sie die Rundungsfehler, die im Zusammenhang mit den Gleitkommatypen stehen.</span><span class="sxs-lookup"><span data-stu-id="07fd3-118">Note the round-off errors that can be associated with the floating-point types.</span></span>

<span data-ttu-id="07fd3-119">Der Restoperator `%` entspricht für die [decimal](../keywords/decimal.md)-Operanden dem [Restoperator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) vom Typ <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="07fd3-119">For the [decimal](../keywords/decimal.md) operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

## <a name="see-also"></a><span data-ttu-id="07fd3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07fd3-120">See also</span></span>

- [<span data-ttu-id="07fd3-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="07fd3-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="07fd3-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="07fd3-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="07fd3-123">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="07fd3-123">C# Operators</span></span>](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
