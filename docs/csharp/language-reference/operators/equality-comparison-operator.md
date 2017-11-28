---
title: "Operator == (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8d778-102">Operator == (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8d778-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="8d778-103">Für vordefinierte Werttypen gibt der Gleichheitsoperator (`==`) TRUE zurück, wenn die Werte der Operanden gleich sind, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8d778-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="8d778-104">Für andere Verweistypen als [string](../../../csharp/language-reference/keywords/string.md) gibt `==` `true` zurück, wenn beide Operanden auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="8d778-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="8d778-105">Für den `string`-Typ vergleicht `==` die Werte der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8d778-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d778-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d778-106">Remarks</span></span>  
 <span data-ttu-id="8d778-107">Benutzerdefinierte Werttypen können den Operator `==` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8d778-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8d778-108">Dies können auch benutzerdefinierte Verweistypen, obwohl `==` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält.</span><span class="sxs-lookup"><span data-stu-id="8d778-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="8d778-109">Wenn `==` überladen ist, muss [!=](../../../csharp/language-reference/operators/not-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="8d778-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="8d778-110">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="8d778-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d778-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d778-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8d778-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d778-112">See Also</span></span>  
 [<span data-ttu-id="8d778-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8d778-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8d778-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8d778-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8d778-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8d778-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
