---
title: Implizit typisierte Arrays (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
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
ms.openlocfilehash: 5a042bdebd07062debe70cbea0a9661fbd425804
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="7fa8d-102">Implizit typisierte Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7fa8d-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="7fa8d-103">Sie können ein implizit typisiertes Array erstellen, in dem der Typ der Arrayinstanz von den im Arrayinitialisierer angegebenen Elementen abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="7fa8d-104">Die Regeln für implizit typisierte Variablen gelten auch für implizit typisierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="7fa8d-105">Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8d-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="7fa8d-106">Implizit typisierte Arrays werden in der Regel in Abfrageausdrücken zusammen mit anonymen Typen sowie Objekt- und Auflistungsinitialisierern verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="7fa8d-107">Die folgenden Beispiele zeigen, wie ein implizit typisiertes Array erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="7fa8d-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 <span data-ttu-id="7fa8d-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7fa8d-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="7fa8d-109">Beachten Sie im vorherigen Beispiel, dass bei implizit typisierten Arrays auf der linken Seite der Initialisierungsanweisung keine eckigen Klammern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-109">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="7fa8d-110">Beachten Sie auch, dass verzweigte Arrays ebenso wie eindimensionale Arrays mithilfe von `new []` initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-110">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="7fa8d-111">Implizit typisierte Arrays in Objektinitialisierern</span><span class="sxs-lookup"><span data-stu-id="7fa8d-111">Implicitly-typed Arrays in Object Initializers</span></span>  
 <span data-ttu-id="7fa8d-112">Beim Erstellen eines anonymen Typs, der ein Array enthält, muss das Array im Objektinitialisierer des Typs implizit typisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-112">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="7fa8d-113">Im folgenden Beispiel ist `contacts` ein implizit typisiertes Array aus anonymen Typen, von denen jeder ein Array mit dem Namen `PhoneNumbers` enthält.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-113">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="7fa8d-114">Beachten Sie, dass das Schlüsselwort `var` nicht in den Objektinitialisierern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fa8d-114">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 <span data-ttu-id="7fa8d-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7fa8d-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa8d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fa8d-116">See Also</span></span>  
 <span data-ttu-id="7fa8d-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7fa8d-118">[Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-118">[Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span></span>  
 <span data-ttu-id="7fa8d-119">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-119">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="7fa8d-120">[Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-120">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="7fa8d-121">[Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-121">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="7fa8d-122">["var"](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="7fa8d-122">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="7fa8d-123">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="7fa8d-123">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

