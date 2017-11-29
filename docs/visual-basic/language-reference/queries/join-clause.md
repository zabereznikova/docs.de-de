---
title: Join-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb25c9dac8994e7f975539c1d036f0f0d9d239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="06ee8-102">Join-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ee8-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="06ee8-103">Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="06ee8-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="06ee8-104">Die Join-Operation wird basierend auf übereinstimmenden Schlüsseln und verwendet die `Equals` Operator.</span><span class="sxs-lookup"><span data-stu-id="06ee8-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ee8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ee8-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="06ee8-106">Teile</span><span class="sxs-lookup"><span data-stu-id="06ee8-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="06ee8-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ee8-107">Required.</span></span> <span data-ttu-id="06ee8-108">Die Steuerelementvariable für die zu verknüpfende Auflistung.</span><span class="sxs-lookup"><span data-stu-id="06ee8-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="06ee8-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ee8-109">Required.</span></span> <span data-ttu-id="06ee8-110">Die Auflistung, die mit der Auflistung auf der linken Seite des kombiniert die `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="06ee8-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="06ee8-111">Ein `Join` Klausel kann geschachtelt sein, in einer anderen `Join` -Klausel, oder in einem `Group Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="06ee8-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="06ee8-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="06ee8-112">Optional.</span></span> <span data-ttu-id="06ee8-113">Eine oder mehrere zusätzliche `Join` Klauseln weiter optimieren der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="06ee8-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="06ee8-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="06ee8-114">Optional.</span></span> <span data-ttu-id="06ee8-115">Eine oder mehrere zusätzliche `Group Join` Klauseln weiter optimieren der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="06ee8-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="06ee8-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="06ee8-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="06ee8-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06ee8-117">Required.</span></span> <span data-ttu-id="06ee8-118">Identifiziert die Schlüssel für die zu verknüpfenden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="06ee8-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="06ee8-119">Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus der zu verknüpfenden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="06ee8-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="06ee8-120">Sie können die Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="06ee8-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="06ee8-121">`key1`muss aus der Auflistung auf der linken Seite von der `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="06ee8-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="06ee8-122">`key2`aus der Auflistung auf der rechten Seite des muss die `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="06ee8-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="06ee8-123">Die in der Joinbedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="06ee8-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="06ee8-124">Jeder Schlüsselausdruck kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="06ee8-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06ee8-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06ee8-125">Remarks</span></span>  
 <span data-ttu-id="06ee8-126">Die `Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Schlüsselwerten von zu verknüpfenden Auflistungen zusammen.</span><span class="sxs-lookup"><span data-stu-id="06ee8-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="06ee8-127">Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung auf der linken Seite des enthalten die `Join` Operator und der Auflistung identifiziert, der `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="06ee8-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="06ee8-128">Die Abfrage gibt nur Ergebnisse für die die Bedingung angegeben werden, indem zurück die `Equals` Operator erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="06ee8-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="06ee8-129">Dies ist gleichbedeutend mit einem `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="06ee8-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="06ee8-130">Sie können mehrere `Join` Klauseln in einer Abfrage mindestens zwei Auflistungen zu einer einzigen Auflistung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="06ee8-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="06ee8-131">Ausführen ein implizites Joins zum Kombinieren von Auflistungen, ohne die `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="06ee8-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="06ee8-132">Um dies zu erreichen, fügen Sie mehrere `In` Klauseln in Ihre `From` Klausel, und geben Sie einen `Where` -Klausel, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="06ee8-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="06ee8-133">Sie können die `Group Join` -Klausel, um Auflistungen zu einer einzelnen hierarchischen Auflistung kombinieren.</span><span class="sxs-lookup"><span data-stu-id="06ee8-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="06ee8-134">Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="06ee8-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ee8-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ee8-135">Example</span></span>  
 <span data-ttu-id="06ee8-136">Das folgende Codebeispiel führt eine implizite Verknüpfung, um eine Liste von Kunden mit ihrer Bestellungen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="06ee8-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="06ee8-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ee8-137">Example</span></span>  
 <span data-ttu-id="06ee8-138">Im folgenden Codebeispiel wird verknüpft zwei Auflistungen mithilfe der `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="06ee8-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="06ee8-139">In diesem Beispiel wird die Ausgabe ähnlich der folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="06ee8-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="06ee8-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06ee8-140">Example</span></span>  
 <span data-ttu-id="06ee8-141">Im folgenden Codebeispiel wird verknüpft zwei Auflistungen mithilfe der `Join` -Klausel mit zwei Schlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="06ee8-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="06ee8-142">Im Beispiel wird die Ausgabe ähnlich der folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="06ee8-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="06ee8-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06ee8-143">See Also</span></span>  
 [<span data-ttu-id="06ee8-144">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06ee8-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="06ee8-145">Abfragen</span><span class="sxs-lookup"><span data-stu-id="06ee8-145">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="06ee8-146">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="06ee8-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="06ee8-147">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="06ee8-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="06ee8-148">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="06ee8-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="06ee8-149">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="06ee8-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
