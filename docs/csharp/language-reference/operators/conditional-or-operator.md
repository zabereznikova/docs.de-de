---
title: "Operator || (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
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
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="8cba3-102">Operator || (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8cba3-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="8cba3-103">Der bedingte Operator OR (`||`) führt ein logisches „Oder“ seiner `bool`-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="8cba3-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="8cba3-104">Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="8cba3-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="8cba3-105">Wenn der erste Operand als `false` ausgewertet wird, wird durch den zweiten Operanden bestimmt, ob der ODER-Ausdruck als Ganzes als `true` oder `false` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8cba3-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cba3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cba3-106">Remarks</span></span>  
 <span data-ttu-id="8cba3-107">Der Vorgang</span><span class="sxs-lookup"><span data-stu-id="8cba3-107">The operation</span></span>  
  
```  
x || y  
```  
  
 <span data-ttu-id="8cba3-108">entspricht dem Vorgang</span><span class="sxs-lookup"><span data-stu-id="8cba3-108">corresponds to the operation</span></span>  
  
```  
x | y  
```  
  
 <span data-ttu-id="8cba3-109">mit folgender Ausnahme: Wenn `x` `true` ist, wird `y` nicht ausgewertet, da der ODER-Vorgang unabhängig des Werts von `y` `true` ist.</span><span class="sxs-lookup"><span data-stu-id="8cba3-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="8cba3-110">Dieses Konzept wird als „Kurzschlussauswertung“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8cba3-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="8cba3-111">Der bedingte ODER-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="8cba3-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cba3-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cba3-112">Example</span></span>  
 <span data-ttu-id="8cba3-113">In den folgenden Beispielen wertet der Ausdruck, der `||` verwendet, nur den ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="8cba3-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="8cba3-114">Der Ausdruck, der `|` verwendet, wertet beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="8cba3-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="8cba3-115">Im zweiten Beispiel tritt eine Laufzeitausnahme auf, wenn beide Operanden ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="8cba3-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 <span data-ttu-id="8cba3-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cba3-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cba3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cba3-117">See Also</span></span>  
 <span data-ttu-id="8cba3-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8cba3-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8cba3-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8cba3-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8cba3-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cba3-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

