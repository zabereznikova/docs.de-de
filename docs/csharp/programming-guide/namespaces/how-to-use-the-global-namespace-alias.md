---
title: 'Gewusst wie: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
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
ms.openlocfilehash: 1252fc107d46b1d3a1cbef0a61708edc57253910
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="e6d3a-102">Gewusst wie: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e6d3a-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="e6d3a-103">Die Möglichkeit, auf einen Member im globalen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zuzugreifen, ist nützlich, wenn der Member möglicherweise von einer anderen Entität mit dem gleichen Namen verdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="e6d3a-104">Im folgenden Code wird `Console` z.B. zu `TestApp.Console` statt zum `Console`-Typ im <xref:System>-Namespace aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 <span data-ttu-id="e6d3a-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-107">Wenn Sie `System.Console` verwenden, führt dies immer noch zu einem Fehler, da der `System`-Namespace von der `TestApp.System`-Klasse verborgen wird:</span><span class="sxs-lookup"><span data-stu-id="e6d3a-107">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 <span data-ttu-id="e6d3a-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-109">Diesen Fehler können Sie jedoch umgehen, indem Sie `global::System.Console` folgendermaßen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e6d3a-109">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 <span data-ttu-id="e6d3a-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-111">Wenn der linke Bezeichner `global` ist, beginnt die Suche nach dem richtigen Bezeichner im globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-111">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="e6d3a-112">Die folgende Deklaration verweist z.B. auf `TestApp` als Member des globalen Spaces.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-112">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 <span data-ttu-id="e6d3a-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-114">Es wird natürlich nicht empfohlen, dass Sie Ihren eigenen Namespace mit dem Namen `System` erstellen, und es ist unwahrscheinlich, dass Sie Code finden, in dem dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-114">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="e6d3a-115">In größeren Projekte ist es jedoch mehr als möglich, dass Namespaceduplikate auf irgendeine Weise vorkommen.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-115">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="e6d3a-116">In derartigen Situationen ist der globale Namespacequalifizierer die Garantie für Sie, den Stammnamespace angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-116">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d3a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6d3a-117">Example</span></span>  
 <span data-ttu-id="e6d3a-118">In diesem Beispiel wird der `System`-Namespace verwendet, um die `TestClass`-Klasse einzubeziehen, weshalb `global::System.Console` verwendet werden muss, um auf die `System.Console`-Klasse zu verweisen, die vom `System`-Namespace verborgen wird.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-118">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="e6d3a-119">Darüber hinaus wird der `colAlias`-Alias verwendet, um auf den `System.Collections`-Namespace zu verweisen. Deshalb wurde die Instanz einer <xref:System.Collections.Hashtable?displayProperty=fullName> mit diesem Alias statt mit dem Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6d3a-119">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=fullName> was created using this alias instead of the namespace.</span></span>  
  
 <span data-ttu-id="e6d3a-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span></span>  
  
 <span data-ttu-id="e6d3a-121">**A 1**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-121">**A 1**</span></span>  
<span data-ttu-id="e6d3a-122">**B 2**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-122">**B 2**</span></span>  
<span data-ttu-id="e6d3a-123">**C 3**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-123">**C 3**</span></span>   
## <a name="see-also"></a><span data-ttu-id="e6d3a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6d3a-124">See Also</span></span>  
 <span data-ttu-id="e6d3a-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6d3a-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e6d3a-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6d3a-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="e6d3a-127">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="e6d3a-127">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="e6d3a-128">[Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="e6d3a-128">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="e6d3a-129">extern</span><span class="sxs-lookup"><span data-stu-id="e6d3a-129">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

