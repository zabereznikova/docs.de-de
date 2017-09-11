---
title: Operator / (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="5cfdf-102">Operator / (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5cfdf-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="5cfdf-103">Der Divisionsoperator (`/`) dividiert seinen ersten Operanden durch den zweiten Operanden.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="5cfdf-104">Alle numerischen Typen besitzen vordefinierte Divisionsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cfdf-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5cfdf-105">Remarks</span></span>  
 <span data-ttu-id="5cfdf-106">Benutzerdefinierte Typen können den Operator `/` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5cfdf-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="5cfdf-107">Eine Überladung des `/`-Operator überlädt implizit den [/= Operator](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5cfdf-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="5cfdf-108">Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="5cfdf-109">Z.B. das Ergebnis von 7 / 3 ist 2.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="5cfdf-110">Bestimmen Sie den Rest von 7 / 3, mithilfe des Restoperator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5cfdf-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="5cfdf-111">Um einen Quotienten als rationale Zahl oder Bruch zu erhalten, geben Sie dem Dividend oder Divisor Typ `float` oder `double`.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="5cfdf-112">Sie können den Typ implizit zuweisen, wenn Sie den Dividenden oder Divisor als Dezimalzahl ausdrücken, indem Sie eine Ziffer rechts neben dem Dezimaltrennzeichen einfügen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cfdf-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cfdf-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5cfdf-113">Example</span></span>  
 <span data-ttu-id="5cfdf-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cfdf-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfdf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cfdf-115">See Also</span></span>  
 <span data-ttu-id="5cfdf-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5cfdf-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5cfdf-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5cfdf-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5cfdf-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5cfdf-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

