---
title: Operator () (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6d62e6c93dcc69c892d4ca96ace3806cb1c8d989
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3cefd-102">Operator () (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3cefd-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="3cefd-103">Zusätzlich zur Angabe der Reihenfolge von Vorgängen in einem Ausdruck werden Klammern verwendet, um folgende Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3cefd-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="3cefd-104">Das Angeben von Umwandlungen oder Typkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="3cefd-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="3cefd-105">Aufrufen von Methoden oder Delegaten.</span><span class="sxs-lookup"><span data-stu-id="3cefd-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="3cefd-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cefd-106">Remarks</span></span>  
 <span data-ttu-id="3cefd-107">Eine Umwandlung ruft implizit den Konvertierungsoperator von einem Typ in einen anderen auf; die Umwandlung schlägt fehl, wenn der Konvertierungsoperator nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3cefd-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="3cefd-108">Weitere Informationen zu Konvertierungsoperatoren erhalten Sie unter [explizit](../../../csharp/language-reference/keywords/explicit.md) und [implizit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="3cefd-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="3cefd-109">Operator `()` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="3cefd-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="3cefd-110">Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="3cefd-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="3cefd-111">Ein CAST-Ausdruck kann zu mehrdeutiger Syntax führen.</span><span class="sxs-lookup"><span data-stu-id="3cefd-111">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="3cefd-112">Der Ausdruck `(x)–y` könnte z.B. entweder als CAST-Ausdruck (eine Umwandlung von –y in Typ x) oder als additiver Ausdruck kombiniert mit einem Ausdruck in Klammern interpretiert werden, der den Wert x–y berechnet.</span><span class="sxs-lookup"><span data-stu-id="3cefd-112">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="3cefd-113">Weitere Informationen zu Methodenaufrufen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="3cefd-113">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3cefd-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="3cefd-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cefd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cefd-115">See Also</span></span>  
 [<span data-ttu-id="3cefd-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3cefd-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3cefd-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3cefd-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3cefd-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="3cefd-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
