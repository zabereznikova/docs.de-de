---
title: new-Einschränkung (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 77c955102ba9cede831c85838a6a7e57025ad35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="275b1-102">new-Einschränkung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="275b1-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="275b1-103">Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="275b1-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="275b1-104">Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="275b1-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="275b1-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="275b1-105">Example</span></span>  
 <span data-ttu-id="275b1-106">Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="275b1-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="275b1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="275b1-107">Example</span></span>  
 <span data-ttu-id="275b1-108">Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="275b1-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="275b1-109">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="275b1-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="275b1-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="275b1-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="275b1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="275b1-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="275b1-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="275b1-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="275b1-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="275b1-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="275b1-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="275b1-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="275b1-115">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="275b1-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="275b1-116">Generika</span><span class="sxs-lookup"><span data-stu-id="275b1-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
