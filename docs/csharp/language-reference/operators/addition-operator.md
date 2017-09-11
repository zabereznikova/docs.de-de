---
title: + Operator (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
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
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="38989-102">Operator + (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="38989-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="38989-103">Der `+`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="38989-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38989-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38989-104">Remarks</span></span>  
 <span data-ttu-id="38989-105">Unäre `+`-Operatoren sind für alle numerischen Typen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="38989-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="38989-106">Das Ergebnis einer unären `+`-Operation für einen numerischen Typ ist nur der Wert des Operanden.</span><span class="sxs-lookup"><span data-stu-id="38989-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="38989-107">Binäre `+`-Operatoren sind für numerische Typen und Zeichenfolgentypen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="38989-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="38989-108">Für numerische Typen berechnet + die Summe der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="38989-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="38989-109">Wenn ein oder beide Operanden vom Typ „String“ sind, verkettet + die Zeichenfolgendarstellungen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="38989-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="38989-110">Delegattypen bieten auch einen binären `+`-Operator, der Delegaten miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="38989-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="38989-111">Benutzerdefinierte Typen können die unären `+`- und binären `+`-Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="38989-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="38989-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="38989-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="38989-113">Weitere Informationen finden Sie unter [Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="38989-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38989-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38989-114">Example</span></span>  
 <span data-ttu-id="38989-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="38989-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="38989-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="38989-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38989-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38989-117">See Also</span></span>  
 <span data-ttu-id="38989-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="38989-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="38989-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="38989-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="38989-120">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="38989-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="38989-121">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="38989-121">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)

