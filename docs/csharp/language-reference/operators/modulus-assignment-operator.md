---
title: Operator %= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9bafd0078153e29fbf923948d9b380d4795c3d35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2b9af-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2b9af-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="2b9af-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="2b9af-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b9af-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b9af-104">Remarks</span></span>  
 <span data-ttu-id="2b9af-105">Ein Ausdruck mit dem Zuweisungsoperator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="2b9af-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="2b9af-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="2b9af-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="2b9af-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="2b9af-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="2b9af-108">Der [Operator %](../../../csharp/language-reference/operators/modulus-operator.md) ist für numerische Typen vordefiniert, um den Rest nach einer Division zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="2b9af-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="2b9af-109">Der Operator `%=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[Operator /](../../../csharp/language-reference/operators/modulus-operator.md) überladen (weitere Informationen unter [operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="2b9af-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b9af-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b9af-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2b9af-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b9af-111">See Also</span></span>  
 [<span data-ttu-id="2b9af-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2b9af-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2b9af-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2b9af-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2b9af-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2b9af-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
