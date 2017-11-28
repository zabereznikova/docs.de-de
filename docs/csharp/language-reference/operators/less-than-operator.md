---
title: '&lt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="cdb9f-102">&lt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cdb9f-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="cdb9f-103">Alle numerischen und Emumerationstypen definieren einen relationalen „weniger als“-Operator (`<`), der `true` zurückgibt, wenn der erste Operand weniger dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="cdb9f-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdb9f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdb9f-104">Remarks</span></span>  
 <span data-ttu-id="cdb9f-105">Benutzerdefinierte Typen können den Operator `<` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="cdb9f-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="cdb9f-106">Wenn `<` überladen ist, muss [>](../../../csharp/language-reference/operators/greater-than-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="cdb9f-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="cdb9f-107">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="cdb9f-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb9f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdb9f-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="cdb9f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdb9f-109">See Also</span></span>  
 [<span data-ttu-id="cdb9f-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cdb9f-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cdb9f-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cdb9f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cdb9f-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="cdb9f-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
