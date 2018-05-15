---
title: Operator |= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: 2abfbcbabb4229049c97aa6827abef3a053d6992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="55158-102">Operator |= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="55158-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="55158-103">Der OR-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="55158-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55158-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55158-104">Remarks</span></span>  
 <span data-ttu-id="55158-105">Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="55158-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="55158-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="55158-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="55158-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="55158-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="55158-108">Der [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="55158-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="55158-109">Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="55158-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55158-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55158-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="55158-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55158-111">See Also</span></span>  
 [<span data-ttu-id="55158-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="55158-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="55158-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="55158-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="55158-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="55158-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
