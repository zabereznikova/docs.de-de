---
title: orderby-Klausel (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc688e7ba164dcca71d13b2d79d30f1373c4778e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="f75a5-102">orderby-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f75a5-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="f75a5-103">In einem Abfrageausdruck bewirkt die `orderby`-Klausel, dass die zurückgegebene Sequenz oder Untersequenz (Gruppe) entweder in aufsteigender oder absteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="f75a5-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="f75a5-104">Es können mehrere Schlüssel angegeben werden, um eine oder mehrere sekundäre Sortiervorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f75a5-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="f75a5-105">Die Sortierung erfolgt mit dem Standardvergleich für den Typ des Elements.</span><span class="sxs-lookup"><span data-stu-id="f75a5-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="f75a5-106">Standardmäßig wird eine aufsteigende Sortierreihenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="f75a5-106">The default sort order is ascending.</span></span> <span data-ttu-id="f75a5-107">Sie können auch einen benutzerdefinierten Vergleich angeben.</span><span class="sxs-lookup"><span data-stu-id="f75a5-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="f75a5-108">Der ist jedoch nur mit der methodenbasierten Syntax verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f75a5-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="f75a5-109">Weitere Informationen finden Sie unter [Sortieren von Daten](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="f75a5-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f75a5-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f75a5-110">Example</span></span>  
 <span data-ttu-id="f75a5-111">Im folgenden Beispiel sortiert die erste Abfrage die Wörter in alphabetischer Reihenfolge, beginnend mit A, und die zweite Abfrage die gleichen Wörter in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f75a5-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="f75a5-112">(Das Schlüsselwort `ascending` ist der Standardwert für das Sortieren und kann ausgelassen werden.)</span><span class="sxs-lookup"><span data-stu-id="f75a5-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="f75a5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f75a5-113">Example</span></span>  
 <span data-ttu-id="f75a5-114">Im folgenden Beispiel wird eine primäre Sortierung der Nachnamen von Studenten und dann eine sekundäre Sortierung auf ihre Vornamen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f75a5-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f75a5-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f75a5-115">Remarks</span></span>  
 <span data-ttu-id="f75a5-116">Zur Kompilierzeit wird die `orderby`-Klausel in einen Aufruf der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode übersetzt.</span><span class="sxs-lookup"><span data-stu-id="f75a5-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="f75a5-117">Mehrere Schlüssel in der `orderby`-Klausel werden in <xref:System.Linq.Enumerable.ThenBy%2A>-Methodenaufrufe übersetzt.</span><span class="sxs-lookup"><span data-stu-id="f75a5-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75a5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f75a5-118">See Also</span></span>  
 [<span data-ttu-id="f75a5-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f75a5-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f75a5-120">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="f75a5-120">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="f75a5-121">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f75a5-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="f75a5-122">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="f75a5-122">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="f75a5-123">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="f75a5-123">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
