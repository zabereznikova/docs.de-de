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
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227986"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="34628-102">Operator + (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="34628-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="34628-103">Der `+`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="34628-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34628-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34628-104">Remarks</span></span>  
 <span data-ttu-id="34628-105">Unäre `+`-Operatoren sind für alle numerischen Typen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="34628-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="34628-106">Das Ergebnis einer unären `+`-Operation für einen numerischen Typ ist nur der Wert des Operanden.</span><span class="sxs-lookup"><span data-stu-id="34628-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="34628-107">Binäre `+`-Operatoren sind für numerische Typen und Zeichenfolgentypen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="34628-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="34628-108">Für numerische Typen berechnet + die Summe der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="34628-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="34628-109">Wenn ein oder beide Operanden vom Typ „String“ sind, verkettet + die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="34628-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="34628-110">Delegattypen bieten auch einen binären `+`-Operator, der Delegaten miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="34628-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="34628-111">Benutzerdefinierte Typen können die unären `+`- und binären `+`-Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="34628-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="34628-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="34628-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="34628-113">Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="34628-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34628-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34628-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="34628-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="34628-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34628-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34628-116">See Also</span></span>

- [<span data-ttu-id="34628-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="34628-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="34628-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="34628-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="34628-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="34628-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="34628-120">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="34628-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
