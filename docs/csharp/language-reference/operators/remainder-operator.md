---
title: Operator % (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e4f20-102">Operator % (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e4f20-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="e4f20-103">Der Restoperator `%` berechnet den Rest nach der Division seines ersten Operanden durch den zweiten.</span><span class="sxs-lookup"><span data-stu-id="e4f20-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="e4f20-104">Alle numerischen Typen besitzen vordefinierte Restoperatoren.</span><span class="sxs-lookup"><span data-stu-id="e4f20-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e4f20-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4f20-105">Remarks</span></span>  
 <span data-ttu-id="e4f20-106">Die Formel `a % b` gibt stets einen Wert im Bereich `(-b, b)` zurück – ausschließlich (es kann nie `b` oder `-b` zurückgegeben werden), wobei das Vorzeichen des Dividenden beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e4f20-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="e4f20-107">Bei der Ganzzahldivision entspricht der Restoperator der Regel `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="e4f20-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="e4f20-108">Dies ist nicht zu verwechseln mit dem kanonischen Modulo, der bei der ganzzahligen Division eine ähnliche Regel erfüllt und Werte im Bereich `[0, b)` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e4f20-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="e4f20-109">C# umfasst keinen Operator für den kanonischen Modulo.</span><span class="sxs-lookup"><span data-stu-id="e4f20-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="e4f20-110">Das Verhalten für positive Dividenden ist jedoch dasselbe.</span><span class="sxs-lookup"><span data-stu-id="e4f20-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="e4f20-111">Benutzerdefinierte Typen können den Operator `%` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e4f20-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e4f20-112">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e4f20-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4f20-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4f20-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="e4f20-114">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e4f20-114">Comments</span></span>  
 <span data-ttu-id="e4f20-115">Beachten Sie die Rundungsfehler im Zusammenhang mit dem double-Typ.</span><span class="sxs-lookup"><span data-stu-id="e4f20-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f20-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4f20-116">See Also</span></span>  
 [<span data-ttu-id="e4f20-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e4f20-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e4f20-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e4f20-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e4f20-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e4f20-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
