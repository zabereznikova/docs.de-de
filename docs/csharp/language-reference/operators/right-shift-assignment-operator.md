---
title: '&gt;Operator &gt;= (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
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
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="8417f-102">&gt;Operator &gt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8417f-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="8417f-103">Der Rechtsschiebezuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="8417f-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8417f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8417f-104">Remarks</span></span>  
 <span data-ttu-id="8417f-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="8417f-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="8417f-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="8417f-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="8417f-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="8417f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8417f-108">Der [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) verschiebt `x` um einen durch `y` angegebenen Wert nach rechts.</span><span class="sxs-lookup"><span data-stu-id="8417f-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="8417f-109">Der >>=-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8417f-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8417f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8417f-110">Example</span></span>  
 <span data-ttu-id="8417f-111">[!code-cs[csRefOperatoren#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8417f-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8417f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8417f-112">See Also</span></span>  
 <span data-ttu-id="8417f-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8417f-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8417f-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8417f-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8417f-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8417f-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

