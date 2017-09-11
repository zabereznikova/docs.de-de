---
title: orderby-Klausel (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
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
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="3dbe9-102">orderby-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3dbe9-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="3dbe9-103">In einem Abfrageausdruck bewirkt die `orderby`-Klausel, dass die zurückgegebene Sequenz oder Untersequenz (Gruppe) entweder in aufsteigender oder absteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="3dbe9-104">Es können mehrere Schlüssel angegeben werden, um eine oder mehrere sekundäre Sortiervorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="3dbe9-105">Die Sortierung erfolgt mit dem Standardvergleich für den Typ des Elements.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="3dbe9-106">Standardmäßig wird eine aufsteigende Sortierreihenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-106">The default sort order is ascending.</span></span> <span data-ttu-id="3dbe9-107">Sie können auch einen benutzerdefinierten Vergleich angeben.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="3dbe9-108">Der ist jedoch nur mit der methodenbasierten Syntax verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="3dbe9-109">Weitere Informationen finden Sie unter [Sortieren von Daten](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span><span class="sxs-lookup"><span data-stu-id="3dbe9-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dbe9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3dbe9-110">Example</span></span>  
 <span data-ttu-id="3dbe9-111">Im folgenden Beispiel sortiert die erste Abfrage die Wörter in alphabetischer Reihenfolge, beginnend mit A, und die zweite Abfrage die gleichen Wörter in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="3dbe9-112">(Das Schlüsselwort `ascending` ist der Standardwert für das Sortieren und kann ausgelassen werden.)</span><span class="sxs-lookup"><span data-stu-id="3dbe9-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="3dbe9-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3dbe9-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dbe9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3dbe9-114">Example</span></span>  
 <span data-ttu-id="3dbe9-115">Im folgenden Beispiel wird eine primäre Sortierung der Nachnamen von Studenten und dann eine sekundäre Sortierung auf ihre Vornamen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="3dbe9-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3dbe9-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dbe9-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3dbe9-117">Remarks</span></span>  
 <span data-ttu-id="3dbe9-118">Zur Kompilierzeit wird die `orderby`-Klausel in einen Aufruf der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode übersetzt.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="3dbe9-119">Mehrere Schlüssel in der `orderby`-Klausel werden in <xref:System.Linq.Enumerable.ThenBy%2A>-Methodenaufrufe übersetzt.</span><span class="sxs-lookup"><span data-stu-id="3dbe9-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbe9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3dbe9-120">See Also</span></span>  
 <span data-ttu-id="3dbe9-121">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dbe9-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3dbe9-122">[Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="3dbe9-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="3dbe9-123">[LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dbe9-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="3dbe9-124">[group-Klausel](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="3dbe9-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="3dbe9-125">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="3dbe9-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

