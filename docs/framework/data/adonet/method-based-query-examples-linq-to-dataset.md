---
title: "Beispiele für die methodenbasierte Abfrage (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 313364f71c463a320816bb92113f3b720146fe25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-examples-linq-to-dataset"></a><span data-ttu-id="67569-102">Beispiele für die methodenbasierte Abfrage (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="67569-102">Method-Based Query Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="67569-103">Dieser Abschnitt enthält [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Programmierbeispiele in methodenbasierter Abfragesyntax, bei denen die Standardabfrageoperatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67569-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples in method-based query syntax that use the standard query operators.</span></span> <span data-ttu-id="67569-104">Die <xref:System.Data.DataSet> in diesen Beispielen verwendet werden ausgefüllt, indem Sie mit der `FillDataSet` -Methode, die im angegebenen [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="67569-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="67569-105">Weitere Informationen finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="67569-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67569-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="67569-106">In This Section</span></span>  
 [<span data-ttu-id="67569-107">Projektion</span><span class="sxs-lookup"><span data-stu-id="67569-107">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
 <span data-ttu-id="67569-108">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.Select%2A> und <xref:System.Linq.Enumerable.SelectMany%2A> ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="67569-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="67569-109">Partitionierung</span><span class="sxs-lookup"><span data-stu-id="67569-109">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
 <span data-ttu-id="67569-110">In den Beispielen in diesem Thema wird gezeigt, wie Sie mit der <xref:System.Linq.Enumerable.Skip%2A>-Methode und der <xref:System.Linq.Enumerable.Take%2A>-Methode ein <xref:System.Data.DataSet> abfragen und die Ergebnisse partitionieren können.</span><span class="sxs-lookup"><span data-stu-id="67569-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="67569-111">Sortierung</span><span class="sxs-lookup"><span data-stu-id="67569-111">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="67569-112">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode, der <xref:System.Linq.Enumerable.OrderByDescending%2A>-Methode, der <xref:System.Linq.Enumerable.Reverse%2A>-Methode und der <xref:System.Linq.Enumerable.ThenByDescending%2A>-Methode ein <xref:System.Data.DataSet> abfragen und die Ergebnisse sortieren können.</span><span class="sxs-lookup"><span data-stu-id="67569-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="67569-113">Set-Operatoren</span><span class="sxs-lookup"><span data-stu-id="67569-113">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
 <span data-ttu-id="67569-114">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Operatoren <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> und <xref:System.Linq.Enumerable.Union%2A> wertbasierte Vergleichsoperationen für einen Satz von Datenzeilen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="67569-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.</span></span>  
  
 [<span data-ttu-id="67569-115">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="67569-115">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
 <span data-ttu-id="67569-116">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> einen Abfrageausdruck sofort ausführen können.</span><span class="sxs-lookup"><span data-stu-id="67569-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 [<span data-ttu-id="67569-117">Elementoperatoren</span><span class="sxs-lookup"><span data-stu-id="67569-117">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
 <span data-ttu-id="67569-118">In den Beispielen in diesem Thema wird gezeigt, wie Sie mit der <xref:System.Linq.Enumerable.First%2A>-Methode und der <xref:System.Linq.Enumerable.ElementAt%2A>-Methode aus einem <xref:System.Data.DataRow><xref:System.Data.DataSet>-Elemente abrufen können.</span><span class="sxs-lookup"><span data-stu-id="67569-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="67569-119">Aggregierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="67569-119">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="67569-120">In den Beispielen in diesem Thema wird gezeigt, wie Sie mit der <xref:System.Linq.Enumerable.Average%2A>-Methode, der <xref:System.Linq.Enumerable.Count%2A>-Methode, der <xref:System.Linq.Enumerable.Max%2A>-Methode, der <xref:System.Linq.Enumerable.Min%2A>-Methode und der <xref:System.Linq.Enumerable.Sum%2A>-Methode ein <xref:System.Data.DataSet> abfragen und die Ergebnisse aggregieren können.</span><span class="sxs-lookup"><span data-stu-id="67569-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="67569-121">Join</span><span class="sxs-lookup"><span data-stu-id="67569-121">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
 <span data-ttu-id="67569-122">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.GroupJoin%2A> und <xref:System.Linq.Enumerable.Join%2A> ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="67569-122">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67569-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67569-123">See Also</span></span>  
 [<span data-ttu-id="67569-124">Beispiele für Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="67569-124">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 [<span data-ttu-id="67569-125">Beispiele für DataSet-spezifische Operatoren</span><span class="sxs-lookup"><span data-stu-id="67569-125">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 [<span data-ttu-id="67569-126">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="67569-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
