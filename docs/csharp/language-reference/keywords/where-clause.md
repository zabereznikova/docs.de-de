---
title: where-Klausel (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="ff338-102">where-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ff338-102">where clause (C# Reference)</span></span>
<span data-ttu-id="ff338-103">Die `where`-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff338-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="ff338-104">Sie wendet eine boolesche Bedingung (*Prädikat*) auf jedes Quellelement an, auf das durch die Bereichsvariable verwiesen wird, und gibt die Elemente zurück, bei denen die angegebene Bedingung wahr ist.</span><span class="sxs-lookup"><span data-stu-id="ff338-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="ff338-105">Ein einzelner Abfrageausdruck enthält möglicherweise mehrere `where`-Klauseln, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff338-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff338-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff338-106">Example</span></span>  
 <span data-ttu-id="ff338-107">Im folgenden Beispiel filtert die `where`-Klausel alle Zahlen mit Ausnahme derjenigen heraus, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="ff338-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="ff338-108">Wenn Sie die `where`-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff338-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="ff338-109">Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff338-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="ff338-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff338-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff338-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff338-111">Example</span></span>  
 <span data-ttu-id="ff338-112">Innerhalb einer einzelnen `where`-Klausel können Sie so viele Prädikate wie nötig angeben, indem Sie die Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff338-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="ff338-113">Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="ff338-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="ff338-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff338-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff338-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff338-115">Example</span></span>  
 <span data-ttu-id="ff338-116">Eine `where`-Klausel kann eine oder mehrere Methoden enthalten, die boolesche Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff338-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="ff338-117">Im folgenden Beispiel verwendet die `where`-Klausel eine Methode, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="ff338-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="ff338-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff338-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff338-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff338-119">Remarks</span></span>  
 <span data-ttu-id="ff338-120">Die `where`-Klausel ist ein Filtermechanismus.</span><span class="sxs-lookup"><span data-stu-id="ff338-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="ff338-121">Sie kann praktisch überall in einem Abfrageausdruck positioniert werden; sie kann allerdings nicht die erste oder letzte Klausel sein.</span><span class="sxs-lookup"><span data-stu-id="ff338-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="ff338-122">Eine `where`-Klausel kann entweder vor oder nach der [group](../../../csharp/language-reference/keywords/group-clause.md)-Klausel angezeigt werden, abhängig davon, ob Sie die Quellelemente vor oder nach deren Gruppierung filtern müssen.</span><span class="sxs-lookup"><span data-stu-id="ff338-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="ff338-123">Wenn ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="ff338-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="ff338-124">Dies ist ein Vorteil der von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] bereitgestellten starken Typprüfung.</span><span class="sxs-lookup"><span data-stu-id="ff338-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="ff338-125">Zur Kompilierzeit wird das Schlüsselwort `where` in einen Aufruf der Standardabfrageoperator-Methode <xref:System.Linq.Enumerable.Where%2A> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ff338-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff338-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff338-126">See Also</span></span>  
 <span data-ttu-id="ff338-127">[Query keywords (LINQ) (Abfrageschlüsselwörter (LINQ))](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ff338-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="ff338-128">[from-Klausel](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ff338-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="ff338-129">[select-Klausel](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ff338-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="ff338-130">[Filtering Data (C#) (Filtern von Daten (C#))](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="ff338-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="ff338-131">[LINQ query expressions (LINQ-Abfrageausdrücke)](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="ff338-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="ff338-132">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="ff338-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

