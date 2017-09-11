---
title: Operator %= (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="7e09d-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7e09d-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="7e09d-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="7e09d-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e09d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e09d-104">Remarks</span></span>  
 <span data-ttu-id="7e09d-105">Ein Ausdruck mit dem Zuweisungsoperator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="7e09d-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="7e09d-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="7e09d-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="7e09d-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="7e09d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="7e09d-108">Der [Operator %](../../../csharp/language-reference/operators/modulus-operator.md) ist für numerische Typen vordefiniert, um den Rest nach einer Division zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="7e09d-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="7e09d-109">Der Operator `%=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[Operator /](../../../csharp/language-reference/operators/modulus-operator.md) überladen (weitere Informationen unter [operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7e09d-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e09d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e09d-110">Example</span></span>  
 <span data-ttu-id="7e09d-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7e09d-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e09d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e09d-112">See Also</span></span>  
 <span data-ttu-id="7e09d-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7e09d-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7e09d-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7e09d-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7e09d-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7e09d-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

