---
title: false-Operator (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: f2001d92e99476131d6f03e13f0bc12104f638b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218257"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="0b190-102">false-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0b190-102">false Operator (C# Reference)</span></span>
<span data-ttu-id="0b190-103">Gibt den [bool](../../../csharp/language-reference/keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand `false` ist, und gibt ansonsten `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="0b190-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="0b190-104">Vor C# 2.0 wurden die Operatoren `true` und `false` verwendet, um benutzerdefinierte Nullable-Werttypen zu erstellen, die mit Typen, wie z. B. `SqlBool` kompatibel waren.</span><span class="sxs-lookup"><span data-stu-id="0b190-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="0b190-105">Jedoch bietet die Sprache jetzt integrierte Unterstützung für Werttypen, die NULL-Werte zulassen, und diese sollten Sie nach Möglichkeit verwendet, anstatt die Operatoren `true` und `false` zu überladen.</span><span class="sxs-lookup"><span data-stu-id="0b190-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="0b190-106">Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b190-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="0b190-107">Bei auf NULL festlegbaren booleschen Werten ist der Ausdruck `a != b` nicht unbedingt gleich `!(a == b)`, da ein oder beide Werte möglicherweise NULL sind.</span><span class="sxs-lookup"><span data-stu-id="0b190-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="0b190-108">Sie müssen sowohl den Operator `true` als auch den Operator `false` separat überladen, um die NULL-Werte im Ausdruck ordnungsgemäß zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0b190-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="0b190-109">Im folgenden Beispiel wird die Überladung und Verwendung der Operatoren `true` und `false` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b190-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 <span data-ttu-id="0b190-110">Ein Typ, der die Operatoren `true` und `false` überlädt, kann für den Kontrollausdruck in den Anweisungen [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) und [for](../../../csharp/language-reference/keywords/for.md) sowie in [bedingten Ausdrücken](../../../csharp/language-reference/operators/conditional-operator.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b190-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="0b190-111">Wenn ein Typ Operator `false` definiert, muss er auch Operator [true](../../../csharp/language-reference/keywords/true.md) definieren.</span><span class="sxs-lookup"><span data-stu-id="0b190-111">If a type defines operator `false`, it must also define operator [true](../../../csharp/language-reference/keywords/true.md).</span></span>  
  
 <span data-ttu-id="0b190-112">Ein Typ kann nicht direkt die bedingten logischen Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) überladen. Jedoch kann ein ähnlicher Effekt erzielt werden, indem die regulären logischen Operatoren sowie die Operatoren `true` und `false` überladen werden.</span><span class="sxs-lookup"><span data-stu-id="0b190-112">A type cannot directly overload the conditional logical operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0b190-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0b190-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b190-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b190-114">See Also</span></span>  
 [<span data-ttu-id="0b190-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0b190-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0b190-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0b190-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0b190-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0b190-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0b190-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0b190-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="0b190-119">true</span><span class="sxs-lookup"><span data-stu-id="0b190-119">true</span></span>](../../../csharp/language-reference/keywords/true.md)
