---
title: Operator / (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8b6f-102">Operator / (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c8b6f-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="c8b6f-103">Der Divisionsoperator (`/`) dividiert seinen ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="c8b6f-104">Alle numerischen Typen besitzen vordefinierte Divisionsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c8b6f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8b6f-105">Remarks</span></span>  
 <span data-ttu-id="c8b6f-106">Benutzerdefinierte Typen können den Operator `/` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="c8b6f-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c8b6f-107">Eine Überladung des `/`-Operator überlädt implizit den [/= Operator](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c8b6f-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="c8b6f-108">Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="c8b6f-109">Z.B. das Ergebnis von 7 / 3 ist 2.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="c8b6f-110">Dies ist nicht zu verwechseln mit der ganzzahligen Division, weil der Operator `/` nach 0 rundet: Das Ergebnis von -7 / 3 ist -2.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="c8b6f-111">Verwenden Sie die Typen `float`, `double` oder `decimal`, um als Quotienten eine rationale Zahl zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="c8b6f-112">Es gibt viele Möglichkeiten für die Konvertierung zwischen [integrierten numerischen Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="c8b6f-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="c8b6f-113">Bestimmen Sie den Rest mithilfe des [Restoperators](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span><span class="sxs-lookup"><span data-stu-id="c8b6f-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8b6f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8b6f-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c8b6f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8b6f-115">See Also</span></span>  
 [<span data-ttu-id="c8b6f-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c8b6f-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c8b6f-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c8b6f-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c8b6f-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c8b6f-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
