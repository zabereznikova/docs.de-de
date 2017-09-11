---
title: Operator () (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
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
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="c15d0-102">Operator () (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c15d0-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="c15d0-103">Zusätzlich zur Angabe der Reihenfolge von Vorgängen in einem Ausdruck werden Klammern verwendet, um folgende Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c15d0-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="c15d0-104">Das Angeben von Umwandlungen oder Typkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="c15d0-104">Specify casts, or type conversions.</span></span>  
  
     <span data-ttu-id="c15d0-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c15d0-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span></span>  
  
2.  <span data-ttu-id="c15d0-106">Aufrufen von Methoden oder Delegaten.</span><span class="sxs-lookup"><span data-stu-id="c15d0-106">Invoke methods or delegates.</span></span>  
  
     <span data-ttu-id="c15d0-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c15d0-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c15d0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c15d0-108">Remarks</span></span>  
 <span data-ttu-id="c15d0-109">Eine Umwandlung ruft implizit den Konvertierungsoperator von einem Typ in einen anderen auf; die Umwandlung schlägt fehl, wenn der Konvertierungsoperator nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c15d0-109">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="c15d0-110">Weitere Informationen zu Konvertierungsoperatoren erhalten Sie unter [explizit](../../../csharp/language-reference/keywords/explicit.md) und [implizit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="c15d0-110">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="c15d0-111">Operator `()` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="c15d0-111">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="c15d0-112">Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="c15d0-112">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="c15d0-113">Ein CAST-Ausdruck kann zu mehrdeutiger Syntax führen.</span><span class="sxs-lookup"><span data-stu-id="c15d0-113">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="c15d0-114">Der Ausdruck `(x)–y` könnte z.B. entweder als CAST-Ausdruck (eine Umwandlung von –y in Typ x) oder als additiver Ausdruck kombiniert mit einem Ausdruck in Klammern interpretiert werden, der den Wert x–y berechnet.</span><span class="sxs-lookup"><span data-stu-id="c15d0-114">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="c15d0-115">Weitere Informationen zu Methodenaufrufen finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="c15d0-115">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c15d0-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c15d0-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c15d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c15d0-117">See Also</span></span>  
 <span data-ttu-id="c15d0-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c15d0-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c15d0-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c15d0-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c15d0-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c15d0-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

