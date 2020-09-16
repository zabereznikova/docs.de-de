---
title: Aggregatabfragen
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 2085808d631d1d9f97573c557e9e66e07113df52
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554220"
---
# <a name="aggregate-queries"></a><span data-ttu-id="7908c-102">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="7908c-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7908c-103">unterstützt die Aggregatoperatoren `Average`, `Count`, `Max`, `Min` und `Sum`.</span><span class="sxs-lookup"><span data-stu-id="7908c-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="7908c-104">Beachten Sie die folgenden Eigenschaften von Aggregatoperatoren in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7908c-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="7908c-105">Aggregatabfragen werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7908c-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="7908c-106">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7908c-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="7908c-107">Aggregatabfragen geben i. d. R. eine Zahl statt einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="7908c-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="7908c-108">Weitere Informationen finden Sie unter [Aggregations Vorgänge](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="7908c-108">For more information, see [Aggregation Operations](/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="7908c-109">Sie können keine Aggregate für anonyme Typen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7908c-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="7908c-110">Die Beispiele in den folgenden Abschnitten leiten sich von der Beispieldatenbank Northwind ab.</span><span class="sxs-lookup"><span data-stu-id="7908c-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="7908c-111">Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7908c-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7908c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7908c-112">In This Section</span></span>  
 [<span data-ttu-id="7908c-113">Zurückgeben des Durchschnittswerts aus einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="7908c-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="7908c-114">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Average%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="7908c-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="7908c-115">Zählen der Anzahl von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="7908c-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="7908c-116">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Count%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="7908c-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="7908c-117">Suchen des maximalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="7908c-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="7908c-118">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Max%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="7908c-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="7908c-119">Suchen des minimalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="7908c-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="7908c-120">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Min%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="7908c-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="7908c-121">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="7908c-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="7908c-122">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Sum%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="7908c-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7908c-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7908c-123">Related Sections</span></span>  
 [<span data-ttu-id="7908c-124">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="7908c-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="7908c-125">Stellt Links zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen in Visual Basic und C# bereit.</span><span class="sxs-lookup"><span data-stu-id="7908c-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="7908c-126">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="7908c-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="7908c-127">Enthält Links zu Themen, in denen Konzepte zum Entwerfen von LINQ-Abfragen in erläutert werden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7908c-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="7908c-128">Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="7908c-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="7908c-129">Erläutert, wie Abfragen in LINQ funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7908c-129">Explains how queries work in LINQ.</span></span>
