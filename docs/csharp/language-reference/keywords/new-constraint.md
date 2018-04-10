---
title: new-Einschränkung (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="dfae7-102">new-Einschränkung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dfae7-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="dfae7-103">Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="dfae7-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="dfae7-104">Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfae7-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfae7-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfae7-105">Example</span></span>  
 <span data-ttu-id="dfae7-106">Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="dfae7-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="dfae7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfae7-107">Example</span></span>  
 <span data-ttu-id="dfae7-108">Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="dfae7-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="dfae7-109">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="dfae7-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dfae7-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dfae7-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfae7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfae7-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="dfae7-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dfae7-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dfae7-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dfae7-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dfae7-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dfae7-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dfae7-115">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dfae7-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="dfae7-116">Generika</span><span class="sxs-lookup"><span data-stu-id="dfae7-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
