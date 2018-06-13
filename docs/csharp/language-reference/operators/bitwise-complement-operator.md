---
title: Operator ~ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 25b157fafde7d2b75cd8b112848a01e9b3fb0db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270302"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="79062-102">Operator ~ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="79062-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="79062-103">Der `~`-Operator führt einen bitweisen komplementären Vorgang für seinen Operanden durch, wodurch jedes Bit umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="79062-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="79062-104">Bitweiser Komplementoperatoren sind für [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) und [ulong](../../../csharp/language-reference/keywords/ulong.md) vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="79062-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79062-105">Das `~`-Symbol wird auch für das Deklarieren von Finalizern verwendet.</span><span class="sxs-lookup"><span data-stu-id="79062-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="79062-106">Weitere Informationen finden Sie unter [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="79062-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79062-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79062-107">Remarks</span></span>  
 <span data-ttu-id="79062-108">Benutzerdefinierte Typen können den Operator `~` überladen.</span><span class="sxs-lookup"><span data-stu-id="79062-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="79062-109">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="79062-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="79062-110">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="79062-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79062-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79062-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="79062-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79062-112">See Also</span></span>  
 [<span data-ttu-id="79062-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="79062-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="79062-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="79062-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79062-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="79062-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="79062-116">Finalizer</span><span class="sxs-lookup"><span data-stu-id="79062-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
