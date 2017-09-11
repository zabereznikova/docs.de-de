---
title: var (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
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
ms.openlocfilehash: 2a96d1c8869edd96cec913f1a868bcc3253dd14f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="var-c-reference"></a><span data-ttu-id="98ad7-102">var (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="98ad7-102">var (C# Reference)</span></span>
<span data-ttu-id="98ad7-103">Ab Visual Studio C# 3.0 können Variablen, die im Methodenbereich deklariert wurden, den impliziten „Typ“ `var` haben.</span><span class="sxs-lookup"><span data-stu-id="98ad7-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="98ad7-104">Eine implizit typisierte lokale Variable ist stark typisiert, als hätten Sie den Typ selbst deklariert. Tatsächlich legt der Compiler den Typ fest.</span><span class="sxs-lookup"><span data-stu-id="98ad7-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="98ad7-105">Die folgenden beiden `i`-Aktivitäten sind funktional äquivalent:</span><span class="sxs-lookup"><span data-stu-id="98ad7-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="98ad7-106">Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Type relationships in LINQ query operations (Typbeziehungen in LINQ-Abfragevorgängen)](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="98ad7-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ad7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98ad7-107">Example</span></span>  
 <span data-ttu-id="98ad7-108">Im folgenden Beispiel werden zwei Abfrageausdrücke gezeigt.</span><span class="sxs-lookup"><span data-stu-id="98ad7-108">The following example shows two query expressions.</span></span> <span data-ttu-id="98ad7-109">Im ersten Ausdruck in das Verwenden von `var` erlaubt aber nicht erforderlich, da der Typ des Abfrageergebnisses explizit als `IEnumerable<string>` angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="98ad7-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="98ad7-110">Im zweiten Ausdruck muss `var` allerdings verwendet werden, weil das Ergebnis eine Auflistung von anonymen Typen ist, und auf die Namen dieser Typen nicht zugegriffen werden kann. Allein der Compiler kann darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="98ad7-110">However, in the second expression, `var` must be used because the result is a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="98ad7-111">Beachten Sie, dass die `foreach`-Iterationsvariable `item` im zweiten Beispiel auch implizit typisiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="98ad7-111">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 <span data-ttu-id="98ad7-112">[!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="98ad7-112">[!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ad7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98ad7-113">See Also</span></span>  
 <span data-ttu-id="98ad7-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="98ad7-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="98ad7-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="98ad7-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="98ad7-116">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="98ad7-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)

