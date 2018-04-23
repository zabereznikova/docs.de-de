---
title: Operator %= (C#-Referenz)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="03b84-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="03b84-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="03b84-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="03b84-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b84-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03b84-104">Remarks</span></span>  
 <span data-ttu-id="03b84-105">Ein Ausdruck mit dem Zuweisungsoperator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="03b84-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="03b84-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="03b84-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="03b84-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="03b84-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="03b84-108">Der [Operator %](../../../csharp/language-reference/operators/remainder-operator.md) ist für numerische Typen vordefiniert, um den Rest nach einer Division zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="03b84-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="03b84-109">Der Operator `%=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[Operator /](../../../csharp/language-reference/operators/remainder-operator.md) überladen (weitere Informationen unter [operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="03b84-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03b84-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03b84-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="03b84-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03b84-111">See Also</span></span>  
 [<span data-ttu-id="03b84-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="03b84-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="03b84-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="03b84-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="03b84-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="03b84-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
