---
title: + Operator (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15d5d1a304569b92b2f811a9ea714e4b30d60d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cd36a-102">Operator + (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cd36a-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="cd36a-103">Der `+`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cd36a-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd36a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd36a-104">Remarks</span></span>  
 <span data-ttu-id="cd36a-105">Unäre `+`-Operatoren sind für alle numerischen Typen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="cd36a-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="cd36a-106">Das Ergebnis einer unären `+`-Operation für einen numerischen Typ ist nur der Wert des Operanden.</span><span class="sxs-lookup"><span data-stu-id="cd36a-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="cd36a-107">Binäre `+`-Operatoren sind für numerische Typen und Zeichenfolgentypen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="cd36a-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="cd36a-108">Für numerische Typen berechnet + die Summe der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="cd36a-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="cd36a-109">Wenn ein oder beide Operanden vom Typ „String“ sind, verkettet + die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="cd36a-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="cd36a-110">Delegattypen bieten auch einen binären `+`-Operator, der Delegaten miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="cd36a-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="cd36a-111">Benutzerdefinierte Typen können die unären `+`- und binären `+`-Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="cd36a-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="cd36a-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="cd36a-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="cd36a-113">Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="cd36a-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd36a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd36a-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="cd36a-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="cd36a-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cd36a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd36a-116">See Also</span></span>  
 [<span data-ttu-id="cd36a-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cd36a-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cd36a-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cd36a-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cd36a-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="cd36a-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="cd36a-120">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cd36a-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
