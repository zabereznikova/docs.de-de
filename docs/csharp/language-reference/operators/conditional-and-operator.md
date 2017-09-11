---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
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
ms.openlocfilehash: 1da61947cbc85e5b3045513e99e013d1e4fae4b3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="32bb7-102">&amp;&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="32bb7-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="32bb7-103">Der bedingte AND-Operator (`&&`) führt eine logische AND-Verknüpfung seiner `bool`-Operanden durch, wertet den zweiten Operanden aber nur dann aus, wenn es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="32bb7-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32bb7-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32bb7-104">Remarks</span></span>  
 <span data-ttu-id="32bb7-105">Der Vorgang</span><span class="sxs-lookup"><span data-stu-id="32bb7-105">The operation</span></span>  
  
```  
x && y  
```  
  
 <span data-ttu-id="32bb7-106">entspricht dem Vorgang</span><span class="sxs-lookup"><span data-stu-id="32bb7-106">corresponds to the operation</span></span>  
  
```  
x & y  
```  
  
 <span data-ttu-id="32bb7-107">mit der Ausnahme, dass `y` nicht ausgewertet wird, wenn `x` `false` ist, weil das Ergebnis der AND-Operation `false` ist, unabhängig vom Wert von `y`.</span><span class="sxs-lookup"><span data-stu-id="32bb7-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="32bb7-108">Dies wird als „Kurzschlussauswertung“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="32bb7-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="32bb7-109">Der bedingte AND-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="32bb7-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32bb7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32bb7-110">Example</span></span>  
 <span data-ttu-id="32bb7-111">Im folgenden Beispiel wertet der bedingte Ausdruck in der zweiten `if`-Anweisung nur den ersten Operanden aus, da der Operand `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="32bb7-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 <span data-ttu-id="32bb7-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="32bb7-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="32bb7-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="32bb7-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32bb7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32bb7-114">See Also</span></span>  
 <span data-ttu-id="32bb7-115">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="32bb7-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="32bb7-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="32bb7-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="32bb7-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="32bb7-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

