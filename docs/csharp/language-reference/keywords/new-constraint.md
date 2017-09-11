---
title: "new-Einschränkung (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="80289-102">new-Einschränkung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="80289-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="80289-103">Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="80289-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="80289-104">Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="80289-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80289-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80289-105">Example</span></span>  
 <span data-ttu-id="80289-106">Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="80289-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="80289-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="80289-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="80289-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80289-108">Example</span></span>  
 <span data-ttu-id="80289-109">Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="80289-109">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 <span data-ttu-id="80289-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="80289-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="80289-111">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="80289-111">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="80289-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="80289-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80289-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80289-113">See Also</span></span>  
 <span data-ttu-id="80289-114"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="80289-114"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="80289-115">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="80289-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="80289-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="80289-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="80289-117">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="80289-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="80289-118">[Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="80289-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="80289-119">Generika</span><span class="sxs-lookup"><span data-stu-id="80289-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

