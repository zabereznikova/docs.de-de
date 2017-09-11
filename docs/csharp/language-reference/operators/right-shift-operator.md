---
title: '&gt;&gt;-Operator (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd3f077e9bb491cefce7db7c015bde201f6f8207
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="8f83c-102">&gt;&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8f83c-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="8f83c-103">Der Right Shift-Operator (`>>`) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8f83c-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f83c-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f83c-104">Remarks</span></span>  
 <span data-ttu-id="8f83c-105">Ist der erste Operand ein [int](../../../csharp/language-reference/keywords/int.md) oder [uint](../../../csharp/language-reference/keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben (zweiter Operand & 0x1F).</span><span class="sxs-lookup"><span data-stu-id="8f83c-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="8f83c-106">Ist der erste Operand ein [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben (zweiter Operand & 0x3F).</span><span class="sxs-lookup"><span data-stu-id="8f83c-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="8f83c-107">Ist der erste Operand ein [int](../../../csharp/language-reference/keywords/int.md) oder [long](../../../csharp/language-reference/keywords/long.md), handelt es sich bei der Verschiebung nach rechts um eine arithmetische Verschiebung (höherwertige leere Bits werden auf das Vorzeichenbit festgelegt).</span><span class="sxs-lookup"><span data-stu-id="8f83c-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="8f83c-108">Ist der erste Operand vom Typ [uint](../../../csharp/language-reference/keywords/uint.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md), handelt es sich bei der Verschiebung nach rechts um eine logische Verschiebung (höherwertige Bits werden mit Nullen angefüllt).</span><span class="sxs-lookup"><span data-stu-id="8f83c-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="8f83c-109">Benutzerdefinierte Typen können den `>>`-Operator überladen. Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="8f83c-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="8f83c-110">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="8f83c-110">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="8f83c-111">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="8f83c-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f83c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f83c-112">Example</span></span>  
 <span data-ttu-id="8f83c-113">[!code-cs[csRefOperatoren#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f83c-113">[!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f83c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f83c-114">See Also</span></span>  
 <span data-ttu-id="8f83c-115">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8f83c-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8f83c-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8f83c-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8f83c-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8f83c-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

