---
title: Operator *= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 465cf37d38a989d5c1bf6f0d0242c295e55684f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0359a-102">Operator \*= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0359a-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="0359a-103">Der binäre Multiplikationszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="0359a-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0359a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0359a-104">Remarks</span></span>  
 <span data-ttu-id="0359a-105">Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="0359a-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="0359a-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="0359a-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="0359a-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0359a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0359a-108">Der [Operator \*](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen und Multiplikationen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="0359a-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="0359a-109">Der Operator `*=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0359a-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0359a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0359a-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0359a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0359a-111">See Also</span></span>  
 [<span data-ttu-id="0359a-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0359a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0359a-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0359a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0359a-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0359a-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
