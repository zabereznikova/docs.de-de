---
title: '&gt;&gt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 7a2992befcacfdc1d9bb968b611051e15702cca8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924823"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="c896a-102">&gt;&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c896a-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="c896a-103">Der Right Shift-Operator (`>>`) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c896a-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c896a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c896a-104">Remarks</span></span>  
 <span data-ttu-id="c896a-105">Ist der erste Operand ein [int](../../../csharp/language-reference/keywords/int.md) oder [uint](../../../csharp/language-reference/keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben (zweiter Operand & 0x1F).</span><span class="sxs-lookup"><span data-stu-id="c896a-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="c896a-106">Ist der erste Operand ein [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben (zweiter Operand & 0x3F).</span><span class="sxs-lookup"><span data-stu-id="c896a-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="c896a-107">Ist der erste Operand ein [int](../../../csharp/language-reference/keywords/int.md) oder [long](../../../csharp/language-reference/keywords/long.md), handelt es sich bei der Verschiebung nach rechts um eine arithmetische Verschiebung (höherwertige leere Bits werden auf das Vorzeichenbit festgelegt).</span><span class="sxs-lookup"><span data-stu-id="c896a-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="c896a-108">Ist der erste Operand vom Typ [uint](../../../csharp/language-reference/keywords/uint.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md), handelt es sich bei der Verschiebung nach rechts um eine logische Verschiebung (höherwertige Bits werden mit Nullen angefüllt).</span><span class="sxs-lookup"><span data-stu-id="c896a-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="c896a-109">Benutzerdefinierte Typen können den `>>`-Operator überladen. Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden [int](../../../csharp/language-reference/keywords/int.md). Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="c896a-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="c896a-110">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="c896a-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c896a-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c896a-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c896a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c896a-112">See Also</span></span>

- [<span data-ttu-id="c896a-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c896a-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c896a-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c896a-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c896a-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c896a-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
