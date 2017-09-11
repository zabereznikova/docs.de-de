---
title: Operator |= (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
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
ms.openlocfilehash: f1c0a92414739efc2ab091871e80852737fdf931
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="ed90a-102">Operator |= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ed90a-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="ed90a-103">Der OR-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="ed90a-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed90a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed90a-104">Remarks</span></span>  
 <span data-ttu-id="ed90a-105">Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="ed90a-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="ed90a-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="ed90a-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="ed90a-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ed90a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ed90a-108">Der [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="ed90a-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="ed90a-109">Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ed90a-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed90a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed90a-110">Example</span></span>  
 <span data-ttu-id="ed90a-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed90a-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed90a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed90a-112">See Also</span></span>  
 <span data-ttu-id="ed90a-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed90a-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ed90a-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed90a-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ed90a-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ed90a-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

