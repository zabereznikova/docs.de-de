---
title: Operator ~ (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
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
ms.openlocfilehash: ffbfc379b7c021ccd8fbed9b796aa9fda6618b55
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="13c09-102">Operator ~ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="13c09-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="13c09-103">Der `~`-Operator führt einen bitweisen komplementären Vorgang für seinen Operanden durch, wodurch jedes Bit umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="13c09-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="13c09-104">Bitweiser Komplementoperatoren sind für [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) und [ulong](../../../csharp/language-reference/keywords/ulong.md) vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="13c09-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c09-105">Das `~`-Symbol wird auch für das Deklarieren von Finalizern verwendet.</span><span class="sxs-lookup"><span data-stu-id="13c09-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="13c09-106">Weitere Informationen finden Sie unter [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="13c09-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13c09-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13c09-107">Remarks</span></span>  
 <span data-ttu-id="13c09-108">Benutzerdefinierte Typen können den Operator `~` überladen.</span><span class="sxs-lookup"><span data-stu-id="13c09-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="13c09-109">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="13c09-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="13c09-110">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="13c09-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c09-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13c09-111">Example</span></span>  
 <span data-ttu-id="13c09-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="13c09-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c09-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13c09-113">See Also</span></span>  
 <span data-ttu-id="13c09-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="13c09-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="13c09-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="13c09-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="13c09-116">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="13c09-116">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="13c09-117">Finalizer</span><span class="sxs-lookup"><span data-stu-id="13c09-117">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

