---
title: Operator || (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 58e5fd72a3748e7af0894093fc461c4efb543608
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925539"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="043a7-102">Operator || (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="043a7-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="043a7-103">Der bedingte Operator OR (`||`) führt ein logisches „Oder“ seiner `bool`-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="043a7-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="043a7-104">Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="043a7-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="043a7-105">Wenn der erste Operand als `false` ausgewertet wird, wird durch den zweiten Operanden bestimmt, ob der ODER-Ausdruck als Ganzes als `true` oder `false` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="043a7-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="043a7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="043a7-106">Remarks</span></span>  
 <span data-ttu-id="043a7-107">Der Vorgang</span><span class="sxs-lookup"><span data-stu-id="043a7-107">The operation</span></span>  
  
```csharp  
x || y  
```  
  
 <span data-ttu-id="043a7-108">entspricht dem Vorgang</span><span class="sxs-lookup"><span data-stu-id="043a7-108">corresponds to the operation</span></span>  
  
```csharp  
x | y  
```  
  
 <span data-ttu-id="043a7-109">mit folgender Ausnahme: Wenn `x` `true` ist, wird `y` nicht ausgewertet, da der ODER-Vorgang unabhängig des Werts von `y` `true` ist.</span><span class="sxs-lookup"><span data-stu-id="043a7-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="043a7-110">Dieses Konzept wird als „Kurzschlussauswertung“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="043a7-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="043a7-111">Der bedingte ODER-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="043a7-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="043a7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="043a7-112">Example</span></span>  
 <span data-ttu-id="043a7-113">In den folgenden Beispielen wertet der Ausdruck, der `||` verwendet, nur den ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="043a7-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="043a7-114">Der Ausdruck, der `|` verwendet, wertet beide Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="043a7-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="043a7-115">Im zweiten Beispiel tritt eine Laufzeitausnahme auf, wenn beide Operanden ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="043a7-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="043a7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="043a7-116">See Also</span></span>

- [<span data-ttu-id="043a7-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="043a7-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="043a7-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="043a7-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="043a7-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="043a7-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
