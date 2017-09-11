---
title: Operator *= (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="bb7de-102">Operator *= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bb7de-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="bb7de-103">Der binäre Multiplikationszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="bb7de-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb7de-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb7de-104">Remarks</span></span>  
 <span data-ttu-id="bb7de-105">Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="bb7de-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="bb7de-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="bb7de-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="bb7de-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="bb7de-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="bb7de-108">Der [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen und Multiplikationen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="bb7de-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="bb7de-109">Der Operator `*=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bb7de-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb7de-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb7de-110">Example</span></span>  
 <span data-ttu-id="bb7de-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb7de-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7de-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb7de-112">See Also</span></span>  
 <span data-ttu-id="bb7de-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb7de-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bb7de-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb7de-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bb7de-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="bb7de-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

