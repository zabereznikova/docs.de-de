---
title: Operator |= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aac4fd6016b65daa15da4bd3a414f385edce7c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ff5e0-102">Operator |= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ff5e0-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="ff5e0-103">Der OR-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="ff5e0-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff5e0-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff5e0-104">Remarks</span></span>  
 <span data-ttu-id="ff5e0-105">Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="ff5e0-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="ff5e0-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="ff5e0-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="ff5e0-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ff5e0-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="ff5e0-108">Der [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="ff5e0-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="ff5e0-109">Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ff5e0-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff5e0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff5e0-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ff5e0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff5e0-111">See Also</span></span>  
 [<span data-ttu-id="ff5e0-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ff5e0-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ff5e0-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ff5e0-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ff5e0-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ff5e0-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
