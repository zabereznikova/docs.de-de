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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a><span data-ttu-id="e8316-102">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="e8316-102">Query Examples</span></span>
<span data-ttu-id="e8316-103">Dieser Abschnitt enthält [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]-Beispiele und C#-Beispiele für typische [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="e8316-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="e8316-104">Entwickler, die [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, finden viele weitere Beispiele in einer Beispiellösung im Abschnitt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8316-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="e8316-105">Weitere Informationen finden Sie unter [Beispiele](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="e8316-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8316-106">*DB* wird häufig in Codebeispielen verwendet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e8316-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="e8316-107">*DB* wird davon ausgegangen, dass eine Instanz von einem *Northwind* -Klasse, die erbt <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="e8316-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8316-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e8316-108">In This Section</span></span>  
 [<span data-ttu-id="e8316-109">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="e8316-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="e8316-110">Beschreibt die Verwendung von <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> etc.</span><span class="sxs-lookup"><span data-stu-id="e8316-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="e8316-111">Zurückgeben des ersten Elements in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e8316-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="e8316-112">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-113">Zurückgeben oder Überspringen von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e8316-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="e8316-114">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-115">Sortieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e8316-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="e8316-116">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-117">Gruppieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e8316-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="e8316-118">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-119">Entfernen von doppelten Elementen aus einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e8316-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="e8316-120">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-121">Bestimmen, ob ein Element oder alle Elemente einer Sequenz eine Bedingung erfüllen</span><span class="sxs-lookup"><span data-stu-id="e8316-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="e8316-122">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.All%2A> und <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-123">Verketten von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="e8316-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="e8316-124">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-125">Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="e8316-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="e8316-126">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-127">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="e8316-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="e8316-128">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-129">Zurückgeben der Vereinigungsmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="e8316-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="e8316-130">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-131">Konvertieren einer Sequenz in ein Array</span><span class="sxs-lookup"><span data-stu-id="e8316-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="e8316-132">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-133">Konvertieren einer Sequenz in eine generische Liste</span><span class="sxs-lookup"><span data-stu-id="e8316-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="e8316-134">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-135">Konvertieren eines Typs in ein generisches „IEnumerable“</span><span class="sxs-lookup"><span data-stu-id="e8316-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="e8316-136">Bietet Beispiele für die Verwendung von <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8316-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="e8316-137">Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="e8316-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="e8316-138">Bietet Beispiele für die Verwendung von Fremdschlüsselnavigation in den Klauseln `from`, `where` und `select`.</span><span class="sxs-lookup"><span data-stu-id="e8316-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="e8316-139">Formulieren von Projektionen</span><span class="sxs-lookup"><span data-stu-id="e8316-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="e8316-140">Bietet Beispiele für die Kombination `select` mit anderen Funktionen (z. B. *anonyme Typen*) um Abfrageprojektionen zu bilden.</span><span class="sxs-lookup"><span data-stu-id="e8316-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e8316-141">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e8316-141">Related Sections</span></span>  
 [<span data-ttu-id="e8316-142">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="e8316-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="e8316-143">Erläutert das Konzept der standardmäßigen Abfrageoperatoren.</span><span class="sxs-lookup"><span data-stu-id="e8316-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="e8316-144">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="e8316-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="e8316-145">Erläutert, wie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Konzepte für Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8316-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="e8316-146">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e8316-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="e8316-147">Bietet ein Portal zu Themen, die Programmierkonzepte für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erläutern.</span><span class="sxs-lookup"><span data-stu-id="e8316-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
