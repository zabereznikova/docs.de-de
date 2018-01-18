---
title: Aggregatabfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a><span data-ttu-id="347d1-102">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="347d1-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="347d1-103"> unterstützt die Aggregatoperatoren `Average`, `Count`, `Max`, `Min` und `Sum`.</span><span class="sxs-lookup"><span data-stu-id="347d1-103"> supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="347d1-104">Beachten Sie die folgenden Eigenschaften von Aggregatoperatoren in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="347d1-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="347d1-105">Aggregatabfragen werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="347d1-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="347d1-106">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="347d1-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="347d1-107">Aggregatabfragen geben i. d. R. eine Zahl statt einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="347d1-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="347d1-108">Weitere Informationen finden Sie unter [Aggregationsvorgänge](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span><span class="sxs-lookup"><span data-stu-id="347d1-108">For more information, see [Aggregation Operations](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span></span>  
  
-   <span data-ttu-id="347d1-109">Sie können keine Aggregate für anonyme Typen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="347d1-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="347d1-110">Die Beispiele in den folgenden Abschnitten leiten sich von der Beispieldatenbank Northwind ab.</span><span class="sxs-lookup"><span data-stu-id="347d1-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="347d1-111">Weitere Informationen finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="347d1-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="347d1-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="347d1-112">In This Section</span></span>  
 [<span data-ttu-id="347d1-113">Zurückgeben des Durchschnittswerts aus einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="347d1-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="347d1-114">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Average%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="347d1-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="347d1-115">Zählen der Anzahl von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="347d1-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="347d1-116">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Count%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="347d1-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="347d1-117">Suchen des maximalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="347d1-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="347d1-118">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Max%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="347d1-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="347d1-119">Suchen des minimalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="347d1-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="347d1-120">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Min%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="347d1-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="347d1-121">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="347d1-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="347d1-122">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Sum%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="347d1-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="347d1-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="347d1-123">Related Sections</span></span>  
 [<span data-ttu-id="347d1-124">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="347d1-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="347d1-125">Stellt Links zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen in Visual Basic und C# bereit.</span><span class="sxs-lookup"><span data-stu-id="347d1-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="347d1-126">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="347d1-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="347d1-127">Stellt Links zu Themen bereit, die Konzepte für das Entwickeln von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erläutern.</span><span class="sxs-lookup"><span data-stu-id="347d1-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="347d1-128">Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="347d1-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="347d1-129">Erklärt, wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] funktionieren.</span><span class="sxs-lookup"><span data-stu-id="347d1-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
