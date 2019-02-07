---
title: <<-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 0271c97bc624a8946b90508e9ce39d217a128c05
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261749"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f9af8-102">\<\<-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f9af8-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="f9af8-103">Der Left Shift-Operator (`<<`) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9af8-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="f9af8-104">Der Typ des zweiten Operanden muss ein [int](../keywords/int.md) oder ein Typ sein, der eine vordefinierte implizite numerische Konvertierung in `int` besitzt.</span><span class="sxs-lookup"><span data-stu-id="f9af8-104">The type of the second operand must be an [int](../keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9af8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9af8-105">Remarks</span></span>

<span data-ttu-id="f9af8-106">Ist der erste Operand ein [int](../keywords/int.md) oder [uint](../keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9af8-106">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="f9af8-107">Die tatsächliche Umschaltanzahl beträgt also 0 bis 31 Bits.</span><span class="sxs-lookup"><span data-stu-id="f9af8-107">That is, the actual shift count is 0 to 31 bits.</span></span>

<span data-ttu-id="f9af8-108">Ist der erste Operand ein [long](../keywords/long.md) oder [ulong](../keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben.</span><span class="sxs-lookup"><span data-stu-id="f9af8-108">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="f9af8-109">Die tatsächliche Umschaltanzahl beträgt also 0 bis 63 Bits.</span><span class="sxs-lookup"><span data-stu-id="f9af8-109">That is, the actual shift count is 0 to 63 bits.</span></span>

<span data-ttu-id="f9af8-110">Alle höherwertigen Bits, die nach der Verschiebung nicht im Bereich des Typs des ersten Operanden liegen, werden verworfen. Die niederwertigen leeren Bits werden mit Nullen angefüllt.</span><span class="sxs-lookup"><span data-stu-id="f9af8-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="f9af8-111">Schiebeoperationen verursachen nie Überläufe.</span><span class="sxs-lookup"><span data-stu-id="f9af8-111">Shift operations never cause overflows.</span></span>

<span data-ttu-id="f9af8-112">Benutzerdefinierte Typen können den `<<`-Operator überladen (siehe [Operator](../keywords/operator.md)). Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden `int`.</span><span class="sxs-lookup"><span data-stu-id="f9af8-112">User-defined types can overload the `<<` operator (see [operator](../keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="f9af8-113">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="f9af8-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="f9af8-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9af8-114">Example</span></span>

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a><span data-ttu-id="f9af8-115">Kommentare</span><span class="sxs-lookup"><span data-stu-id="f9af8-115">Comments</span></span>

<span data-ttu-id="f9af8-116">Beachten Sie, dass `i<<1` und `i<<33` dasselbe Ergebnis liefern, da die fünf niederwertigen Bits von 1 und 33 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f9af8-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9af8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9af8-117">See also</span></span>

- [<span data-ttu-id="f9af8-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f9af8-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9af8-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f9af8-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9af8-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f9af8-120">C# Operators</span></span>](index.md)
