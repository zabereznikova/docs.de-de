---
title: Operator () (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 82dfc2e11d6a8a025aa9b7557255a13b69ffa508
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208070"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f257a-102">Operator () (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f257a-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="f257a-103">Zusätzlich zur Angabe der Reihenfolge von Vorgängen in einem Ausdruck werden Klammern verwendet, um folgende Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f257a-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="f257a-104">Das Angeben von Umwandlungen oder Typkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="f257a-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="f257a-105">Aufrufen von Methoden oder Delegaten.</span><span class="sxs-lookup"><span data-stu-id="f257a-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f257a-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f257a-106">Remarks</span></span>  
 <span data-ttu-id="f257a-107">Eine Umwandlung ruft implizit den Konvertierungsoperator von einem Typ in einen anderen auf; die Umwandlung schlägt fehl, wenn der Konvertierungsoperator nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f257a-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="f257a-108">Weitere Informationen zu Konvertierungsoperatoren erhalten Sie unter [explizit](../../../csharp/language-reference/keywords/explicit.md) und [implizit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="f257a-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="f257a-109">Operator `()` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="f257a-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="f257a-110">Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f257a-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="f257a-111">Weitere Informationen zu Methodenaufrufen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="f257a-111">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f257a-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f257a-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f257a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f257a-113">See Also</span></span>  
 [<span data-ttu-id="f257a-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f257a-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f257a-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f257a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f257a-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f257a-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
