---
title: "Operator % (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="65ec8-102">Operator % (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="65ec8-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="65ec8-103">Der Operator `%` berechnet den Rest nach der Division seines ersten Operanden durch den zweiten.</span><span class="sxs-lookup"><span data-stu-id="65ec8-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="65ec8-104">Alle numerischen Typen besitzen vordefinierte Restoperatoren.</span><span class="sxs-lookup"><span data-stu-id="65ec8-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65ec8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65ec8-105">Remarks</span></span>  
 <span data-ttu-id="65ec8-106">Benutzerdefinierte Typen können den Operator `%` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="65ec8-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="65ec8-107">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="65ec8-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ec8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65ec8-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="65ec8-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="65ec8-109">Comments</span></span>  
 <span data-ttu-id="65ec8-110">Beachten Sie die Rundungsfehler im Zusammenhang mit dem double-Typ.</span><span class="sxs-lookup"><span data-stu-id="65ec8-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ec8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65ec8-111">See Also</span></span>  
 [<span data-ttu-id="65ec8-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="65ec8-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="65ec8-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="65ec8-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="65ec8-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="65ec8-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
