---
title: Operator / (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: bddf6d234f3536ad64f0cd876cc7ade4494916d9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43394852"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="92d14-102">Operator / (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="92d14-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="92d14-103">Der Divisionsoperator (`/`) dividiert seinen ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="92d14-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="92d14-104">Alle numerischen Typen besitzen vordefinierte Divisionsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="92d14-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="92d14-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92d14-105">Remarks</span></span>  
 <span data-ttu-id="92d14-106">Benutzerdefinierte Typen können den Operator `/` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="92d14-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="92d14-107">Eine Überladung des `/`-Operator überlädt implizit den [/= Operator](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="92d14-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="92d14-108">Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="92d14-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="92d14-109">Z.B. das Ergebnis von 7 / 3 ist 2.</span><span class="sxs-lookup"><span data-stu-id="92d14-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="92d14-110">Dies ist nicht zu verwechseln mit der ganzzahligen Division, weil der Operator `/` nach 0 rundet: Das Ergebnis von -7 / 3 ist -2.</span><span class="sxs-lookup"><span data-stu-id="92d14-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="92d14-111">Verwenden Sie die Typen `float`, `double` oder `decimal`, um als Quotienten eine rationale Zahl zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="92d14-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="92d14-112">Es gibt viele Möglichkeiten für die Konvertierung zwischen [integrierten numerischen Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="92d14-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="92d14-113">Bestimmen Sie den Rest mithilfe des [Restoperators](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span><span class="sxs-lookup"><span data-stu-id="92d14-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92d14-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92d14-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="92d14-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92d14-115">See Also</span></span>

- [<span data-ttu-id="92d14-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92d14-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="92d14-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="92d14-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="92d14-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="92d14-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
