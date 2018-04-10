---
title: where-Klausel (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0324346ee5e214bf467fcb522ef781c91fa1b76f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="23bc7-102">where-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="23bc7-102">where clause (C# Reference)</span></span>
<span data-ttu-id="23bc7-103">Die `where`-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="23bc7-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="23bc7-104">Sie wendet eine boolesche Bedingung (*Prädikat*) auf jedes Quellelement an, auf das durch die Bereichsvariable verwiesen wird, und gibt die Elemente zurück, bei denen die angegebene Bedingung wahr ist.</span><span class="sxs-lookup"><span data-stu-id="23bc7-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="23bc7-105">Ein einzelner Abfrageausdruck enthält möglicherweise mehrere `where`-Klauseln, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.</span><span class="sxs-lookup"><span data-stu-id="23bc7-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23bc7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23bc7-106">Example</span></span>  
 <span data-ttu-id="23bc7-107">Im folgenden Beispiel filtert die `where`-Klausel alle Zahlen mit Ausnahme derjenigen heraus, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="23bc7-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="23bc7-108">Wenn Sie die `where`-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23bc7-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="23bc7-109">Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="23bc7-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="23bc7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23bc7-110">Example</span></span>  
 <span data-ttu-id="23bc7-111">Innerhalb einer einzelnen `where`-Klausel können Sie so viele Prädikate wie nötig angeben, indem Sie die Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="23bc7-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="23bc7-112">Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="23bc7-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="23bc7-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23bc7-113">Example</span></span>  
 <span data-ttu-id="23bc7-114">Eine `where`-Klausel kann eine oder mehrere Methoden enthalten, die boolesche Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="23bc7-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="23bc7-115">Im folgenden Beispiel verwendet die `where`-Klausel eine Methode, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="23bc7-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="23bc7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23bc7-116">Remarks</span></span>  
 <span data-ttu-id="23bc7-117">Die `where`-Klausel ist ein Filtermechanismus.</span><span class="sxs-lookup"><span data-stu-id="23bc7-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="23bc7-118">Sie kann praktisch überall in einem Abfrageausdruck positioniert werden; sie kann allerdings nicht die erste oder letzte Klausel sein.</span><span class="sxs-lookup"><span data-stu-id="23bc7-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="23bc7-119">Eine `where`-Klausel kann entweder vor oder nach der [group](../../../csharp/language-reference/keywords/group-clause.md)-Klausel angezeigt werden, abhängig davon, ob Sie die Quellelemente vor oder nach deren Gruppierung filtern müssen.</span><span class="sxs-lookup"><span data-stu-id="23bc7-119">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="23bc7-120">Wenn ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="23bc7-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="23bc7-121">Dies ist ein Vorteil der von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] bereitgestellten starken Typprüfung.</span><span class="sxs-lookup"><span data-stu-id="23bc7-121">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="23bc7-122">Zur Kompilierzeit wird das Schlüsselwort `where` in einen Aufruf der Standardabfrageoperator-Methode <xref:System.Linq.Enumerable.Where%2A> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="23bc7-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bc7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23bc7-123">See Also</span></span>  
 [<span data-ttu-id="23bc7-124">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="23bc7-124">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="23bc7-125">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="23bc7-125">from clause</span></span>](../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="23bc7-126">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="23bc7-126">select clause</span></span>](../../../csharp/language-reference/keywords/select-clause.md)  
 [<span data-ttu-id="23bc7-127">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="23bc7-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)  
 [<span data-ttu-id="23bc7-128">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="23bc7-128">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="23bc7-129">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="23bc7-129">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
