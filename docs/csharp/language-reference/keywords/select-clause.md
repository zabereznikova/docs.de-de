---
title: select-Klausel (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
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
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a><span data-ttu-id="abd89-102">select-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="abd89-102">select clause (C# Reference)</span></span>
<span data-ttu-id="abd89-103">In einem Abfrageausdruck gibt die `select`-Klausel den Typ der Werte an, die beim Ausführen der Abfrage erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="abd89-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="abd89-104">Das Ergebnis basiert auf der Auswertung aller vorherigen Klauseln und auf allen Ausdrücke in der `select`-Klausel selbst.</span><span class="sxs-lookup"><span data-stu-id="abd89-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="abd89-105">Ein Abfrageausdruck muss entweder mit einer `select`-Klausel oder einer [group](../../../csharp/language-reference/keywords/group-clause.md)-Klausel enden.</span><span class="sxs-lookup"><span data-stu-id="abd89-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="abd89-106">Im folgenden Beispiel wird eine einfache `select`-Klausel in einem Abfrageausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="abd89-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 <span data-ttu-id="abd89-107">[!code-cs[cscsrefAbfrageSchlüsselwörter#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abd89-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="abd89-108">Der Typ der mit der `select`-Klausel erstellten Sequenz bestimmt den Typ der Abfragevariable `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="abd89-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="abd89-109">Im einfachsten Fall gibt die `select`-Klausel nur die Bereichsvariable an.</span><span class="sxs-lookup"><span data-stu-id="abd89-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="abd89-110">Dadurch enthält die zurückgegebene Sequenz Elemente desselben Typs wie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="abd89-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="abd89-111">Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="abd89-111">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="abd89-112">Allerdings bietet die `select`-Klausel zudem ein leistungsstarkes Werkzeug, um Quelldaten in neue Typen zu transformieren (oder zu *projizieren*).</span><span class="sxs-lookup"><span data-stu-id="abd89-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="abd89-113">Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="abd89-113">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abd89-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abd89-114">Example</span></span>  
 <span data-ttu-id="abd89-115">Das folgende Beispiel zeigt die verschiedenen Formen, die eine `select`-Klausel annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="abd89-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="abd89-116">Beachten Sie in jeder Abfrage die Beziehung zwischen der `select`-Klausel und dem Typ der *Abfragevariable* (`studentQuery1`, `studentQuery2` usw.).</span><span class="sxs-lookup"><span data-stu-id="abd89-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 <span data-ttu-id="abd89-117">[!code-cs[cscsrefAbfrageSchlüsselwörter#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="abd89-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="abd89-118">Wie in `studentQuery8` im vorherigen Beispiel kann es möglicherweise sinnvoll sein, dass die Elemente der zurückgegebenen Sequenz nur eine Teilmenge der Eigenschaften der Quellelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="abd89-118">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="abd89-119">Indem die zurückgegebene Sequenz so klein wie möglich gehalten wird, können die Speicheranforderungen reduziert und die Geschwindigkeit der Abfrageausführung erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="abd89-119">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="abd89-120">Erstellen Sie hierzu einen anonymen Typ in der `select`-Klausel, und verwenden Sie einen Objektinitialisierer, um sie mit den entsprechenden Eigenschaften aus dem Quellelement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="abd89-120">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="abd89-121">Ein Beispiel zur Vorgehensweise finden Sie unter [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="abd89-121">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abd89-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abd89-122">Remarks</span></span>  
 <span data-ttu-id="abd89-123">Beim Kompilieren wird die `select`-Klausel in einen Methodenaufruf des <xref:System.Linq.Enumerable.Select%2A>-Standardabfrageoperators übersetzt.</span><span class="sxs-lookup"><span data-stu-id="abd89-123">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd89-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abd89-124">See Also</span></span>  
 <span data-ttu-id="abd89-125">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="abd89-126">[Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-126">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="abd89-127">[from-Klausel](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-127">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="abd89-128">[partial (Methode) (C#-Referenz)](../../../csharp/language-reference/keywords/partial-method.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-128">[partial (Method) (C# Reference)](../../../csharp/language-reference/keywords/partial-method.md) </span></span>  
 <span data-ttu-id="abd89-129">[Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-129">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="abd89-130">[LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="abd89-130">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="abd89-131">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="abd89-131">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

