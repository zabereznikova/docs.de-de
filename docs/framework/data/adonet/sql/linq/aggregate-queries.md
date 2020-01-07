---
title: Aggregatabfragen
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8defefb39974bea150fed84b0e7404b43882c41c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634741"
---
# <a name="aggregate-queries"></a><span data-ttu-id="e93ee-102">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="e93ee-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e93ee-103">unterstützt die Aggregatoperatoren `Average`, `Count`, `Max`, `Min` und `Sum`.</span><span class="sxs-lookup"><span data-stu-id="e93ee-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="e93ee-104">Beachten Sie die folgenden Eigenschaften von Aggregatoperatoren in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e93ee-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="e93ee-105">Aggregatabfragen werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e93ee-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="e93ee-106">Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e93ee-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="e93ee-107">Aggregatabfragen geben i. d. R. eine Zahl statt einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="e93ee-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="e93ee-108">Weitere Informationen finden Sie unter [Aggregations Vorgänge](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="e93ee-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="e93ee-109">Sie können keine Aggregate für anonyme Typen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e93ee-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="e93ee-110">Die Beispiele in den folgenden Abschnitten leiten sich von der Beispieldatenbank Northwind ab.</span><span class="sxs-lookup"><span data-stu-id="e93ee-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="e93ee-111">Weitere Informationen finden Sie unter [Herunterladen von Beispiel Datenbanken](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e93ee-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e93ee-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e93ee-112">In This Section</span></span>  
 [<span data-ttu-id="e93ee-113">Zurückgeben des Durchschnittswerts aus einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="e93ee-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="e93ee-114">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Average%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="e93ee-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="e93ee-115">Zählen der Anzahl von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e93ee-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="e93ee-116">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Count%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="e93ee-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="e93ee-117">Suchen des maximalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="e93ee-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="e93ee-118">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Max%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="e93ee-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="e93ee-119">Suchen des minimalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="e93ee-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="e93ee-120">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Min%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="e93ee-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="e93ee-121">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="e93ee-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="e93ee-122">Zeigt die Verwendung des <xref:System.Linq.Enumerable.Sum%2A>-Operators.</span><span class="sxs-lookup"><span data-stu-id="e93ee-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e93ee-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e93ee-123">Related Sections</span></span>  
 [<span data-ttu-id="e93ee-124">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="e93ee-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="e93ee-125">Stellt Links zu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen in Visual Basic und C# bereit.</span><span class="sxs-lookup"><span data-stu-id="e93ee-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="e93ee-126">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="e93ee-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="e93ee-127">Enthält Links zu Themen, in denen Konzepte zum Entwerfen von LINQ-Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="e93ee-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="e93ee-128">Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="e93ee-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="e93ee-129">Erläutert, wie Abfragen in LINQ funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e93ee-129">Explains how queries work in LINQ.</span></span>
