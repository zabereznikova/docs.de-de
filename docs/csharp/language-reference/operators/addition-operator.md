---
title: + Operator (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d4a269c07e0d6dc2ac6a6a101f200653c6ea7a29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267406"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="22088-102">Operator + (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22088-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="22088-103">Der `+`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="22088-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22088-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22088-104">Remarks</span></span>  
 <span data-ttu-id="22088-105">Unäre `+`-Operatoren sind für alle numerischen Typen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="22088-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="22088-106">Das Ergebnis einer unären `+`-Operation für einen numerischen Typ ist nur der Wert des Operanden.</span><span class="sxs-lookup"><span data-stu-id="22088-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="22088-107">Binäre `+`-Operatoren sind für numerische Typen und Zeichenfolgentypen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="22088-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="22088-108">Für numerische Typen berechnet + die Summe der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="22088-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="22088-109">Wenn ein oder beide Operanden vom Typ „String“ sind, verkettet + die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="22088-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="22088-110">Delegattypen bieten auch einen binären `+`-Operator, der Delegaten miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="22088-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="22088-111">Benutzerdefinierte Typen können die unären `+`- und binären `+`-Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="22088-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="22088-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="22088-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="22088-113">Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="22088-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22088-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22088-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="22088-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="22088-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22088-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22088-116">See Also</span></span>  
 [<span data-ttu-id="22088-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="22088-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="22088-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="22088-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="22088-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="22088-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="22088-120">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22088-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
