---
title: Abfragebeispiele
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e7d7a0a1f641603887675ed0c1faebd5c06b273
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="query-examples"></a><span data-ttu-id="c52c7-102">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="c52c7-102">Query Examples</span></span>
<span data-ttu-id="c52c7-103">Dieser Abschnitt enthält [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Beispiele und C#-Beispiele für typische [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c52c7-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="c52c7-104">Entwickler, die [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, finden viele weitere Beispiele in einer Beispiellösung im Abschnitt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c52c7-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="c52c7-105">Weitere Informationen finden Sie unter [Beispiele](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="c52c7-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c52c7-106">*DB* wird häufig in Codebeispielen verwendet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c52c7-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="c52c7-107">*DB* wird davon ausgegangen, dass eine Instanz von einem *Northwind* -Klasse, die erbt <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c52c7-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c52c7-108">In This Section</span></span>  
 [<span data-ttu-id="c52c7-109">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="c52c7-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="c52c7-110">Beschreibt die Verwendung von <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> etc.</span><span class="sxs-lookup"><span data-stu-id="c52c7-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="c52c7-111">Zurückgeben des ersten Elements in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="c52c7-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="c52c7-112">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-113">Zurückgeben oder Überspringen von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="c52c7-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="c52c7-114">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-115">Sortieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="c52c7-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="c52c7-116">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-117">Gruppieren Sie Elemente in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="c52c7-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="c52c7-118">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-119">Entfernen von doppelten Elementen aus einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="c52c7-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="c52c7-120">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-121">Bestimmen Sie, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c52c7-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="c52c7-122">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.All%2A> und <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-123">Verketten von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="c52c7-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="c52c7-124">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-125">Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="c52c7-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="c52c7-126">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-127">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="c52c7-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="c52c7-128">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-129">Zurückgeben der Vereinigungsmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="c52c7-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="c52c7-130">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-131">Konvertieren einer Sequenz in ein Array</span><span class="sxs-lookup"><span data-stu-id="c52c7-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="c52c7-132">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-133">Konvertieren einer Sequenz in eine generische Liste</span><span class="sxs-lookup"><span data-stu-id="c52c7-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="c52c7-134">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-135">Konvertieren eines Typs in eine generische "IEnumerable"</span><span class="sxs-lookup"><span data-stu-id="c52c7-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="c52c7-136">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="c52c7-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="c52c7-137">Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="c52c7-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="c52c7-138">Bietet Beispiele für die Verwendung von Fremdschlüsselnavigation in den Klauseln `from`, `where` und `select`.</span><span class="sxs-lookup"><span data-stu-id="c52c7-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="c52c7-139">Formulieren von Projektionen</span><span class="sxs-lookup"><span data-stu-id="c52c7-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="c52c7-140">Bietet Beispiele für die Kombination `select` mit anderen Funktionen (z. B. *anonyme Typen*) um Abfrageprojektionen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="c52c7-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c52c7-141">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c52c7-141">Related Sections</span></span>  
 [<span data-ttu-id="c52c7-142">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="c52c7-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="c52c7-143">Erläutert das Konzept der standardmäßigen Abfrageoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c52c7-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="c52c7-144">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="c52c7-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="c52c7-145">Erläutert, wie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Konzepte für Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c52c7-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="c52c7-146">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c52c7-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="c52c7-147">Bietet ein Portal zu Themen, die Programmierkonzepte für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erläutern.</span><span class="sxs-lookup"><span data-stu-id="c52c7-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
