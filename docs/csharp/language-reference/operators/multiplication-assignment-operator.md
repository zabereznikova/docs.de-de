---
title: Operator *= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc2201f78e1e05bd0ccdea04522896c00294bdd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a7b83-102">Operator \*= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a7b83-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="a7b83-103">Der binäre Multiplikationszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="a7b83-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7b83-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7b83-104">Remarks</span></span>  
 <span data-ttu-id="a7b83-105">Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="a7b83-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="a7b83-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a7b83-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="a7b83-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a7b83-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="a7b83-108">Der [Operator \*](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen und Multiplikationen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="a7b83-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="a7b83-109">Der Operator `*=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a7b83-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7b83-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7b83-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a7b83-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7b83-111">See Also</span></span>  
 [<span data-ttu-id="a7b83-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a7b83-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a7b83-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a7b83-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a7b83-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a7b83-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
