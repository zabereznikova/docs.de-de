---
title: true-Operator (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
ms.openlocfilehash: 54b8d764dc673598474d6adbbee82e0223a16b93
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994584"
---
# <a name="true-operator-c-reference"></a><span data-ttu-id="ff3c9-102">true-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ff3c9-102">true Operator (C# Reference)</span></span>
<span data-ttu-id="ff3c9-103">Gibt den [bool](../../../csharp/language-reference/keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand TRUE ist, und gibt ansonsten `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is true and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="ff3c9-104">Vor C#-2.0 wurden die Operatoren `true` und `false` verwendet, um benutzerdefinierte Werttypen, die NULL-Werte zulassen, zu erstellen, die mit Typen, wie z.B. `SqlBool`, kompatibel waren.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="ff3c9-105">Jedoch bietet die Sprache jetzt integrierte Unterstützung für Werttypen, die NULL-Werte zulassen, und diese sollten Sie nach Möglichkeit verwendet, anstatt die Operatoren `true` und `false` zu überladen.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="ff3c9-106">Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff3c9-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="ff3c9-107">Bei booleschen Werten, die NULL-Werte zulassen, ist der Ausdruck `a != b` nicht unbedingt gleich `!(a == b)`, da ein oder beide Werte möglicherweise NULL sind.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="ff3c9-108">Sie müssen sowohl den Operator `true` als auch den Operator `false` separat überladen, um die NULL-Werte im Ausdruck ordnungsgemäß zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-108">You need to overload both the `true` and `false` operators separately to correctly identify the null values in the expression.</span></span> <span data-ttu-id="ff3c9-109">Im folgenden Beispiel wird die Überladung und Verwendung der Operatoren `true` und `false` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 <span data-ttu-id="ff3c9-110">Ein Typ, der die Operatoren `true` und `false` überlädt, kann für den Kontrollausdruck in den Anweisungen [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) und [for](../../../csharp/language-reference/keywords/for.md) sowie in [bedingten Ausdrücken](../../../csharp/language-reference/operators/conditional-operator.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="ff3c9-111">Wenn ein Typ Operator `true` definiert, muss er auch Operator [false](../../../csharp/language-reference/keywords/false.md) definieren.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-111">If a type defines operator `true`, it must also define operator [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
 <span data-ttu-id="ff3c9-112">Ein Typ kann nicht direkt die bedingten logischen Operatoren ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)) überladen. Jedoch kann ein ähnlicher Effekt erzielt werden, indem die regulären logischen Operatoren sowie die Operatoren `true` und `false` überladen werden.</span><span class="sxs-lookup"><span data-stu-id="ff3c9-112">A type cannot directly overload the conditional logical operators ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ff3c9-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ff3c9-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff3c9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff3c9-114">See Also</span></span>

- [<span data-ttu-id="ff3c9-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ff3c9-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ff3c9-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ff3c9-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ff3c9-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ff3c9-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ff3c9-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ff3c9-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="ff3c9-119">false</span><span class="sxs-lookup"><span data-stu-id="ff3c9-119">false</span></span>](../../../csharp/language-reference/keywords/false.md)
