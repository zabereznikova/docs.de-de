---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 15bb3e9702f04cc805af63767c7ecbfc68160368
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171914"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="e601d-102">&amp;&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e601d-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="e601d-103">Der bedingte AND-Operator (`&&`) führt eine logische AND-Verknüpfung seiner `bool`-Operanden durch, wertet aber falls erforderlich nur den zweiten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="e601d-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e601d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e601d-104">Remarks</span></span>  
 <span data-ttu-id="e601d-105">Der Vorgang</span><span class="sxs-lookup"><span data-stu-id="e601d-105">The operation</span></span>  
  
```csharp  
x && y  
```  
  
 <span data-ttu-id="e601d-106">entspricht dem Vorgang</span><span class="sxs-lookup"><span data-stu-id="e601d-106">corresponds to the operation</span></span>  
  
```csharp  
x & y  
```  
  
 <span data-ttu-id="e601d-107">mit der Ausnahme, dass `y` nicht ausgewertet wird, wenn `x` `false` ist, weil das Ergebnis der AND-Operation `false` ist, unabhängig vom Wert von `y`.</span><span class="sxs-lookup"><span data-stu-id="e601d-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="e601d-108">Dies wird als „Kurzschlussauswertung“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e601d-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="e601d-109">Der bedingte AND-Operator kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der Operatoren [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md) gelten mit gewissen Einschränkungen auch als Überladungen der bedingten logischen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e601d-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e601d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e601d-110">Example</span></span>  
 <span data-ttu-id="e601d-111">Im folgenden Beispiel wertet der bedingte Ausdruck in der zweiten `if`-Anweisung nur den ersten Operanden aus, da der Operand `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e601d-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e601d-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e601d-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e601d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e601d-113">See Also</span></span>  
 [<span data-ttu-id="e601d-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e601d-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e601d-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e601d-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e601d-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e601d-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
