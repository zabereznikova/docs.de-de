---
title: Join-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 21432b95b30ae38ac2cbc9e55b5a3066f0bef665
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825845"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="07c8a-102">Join-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07c8a-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="07c8a-103">Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="07c8a-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="07c8a-104">Die Join-Operation wird auf Grundlage übereinstimmender Schlüssel und verwendet die `Equals` Operator.</span><span class="sxs-lookup"><span data-stu-id="07c8a-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c8a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07c8a-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="07c8a-106">Teile</span><span class="sxs-lookup"><span data-stu-id="07c8a-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="07c8a-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="07c8a-107">Required.</span></span> <span data-ttu-id="07c8a-108">Die Steuerelementvariable für die Sammlung verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="07c8a-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="07c8a-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="07c8a-109">Required.</span></span> <span data-ttu-id="07c8a-110">Die Auflistung, die mit der Auflistung auf der linken Seite des kombiniert die `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="07c8a-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="07c8a-111">Ein `Join` -Klausel kann in einer anderen geschachtelt werden `Join` -Klausel oder in einem `Group Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="07c8a-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="07c8a-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="07c8a-112">Optional.</span></span> <span data-ttu-id="07c8a-113">Eine oder mehrere zusätzliche `Join` -Klauseln zum weiteren Optimieren der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="07c8a-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="07c8a-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="07c8a-114">Optional.</span></span> <span data-ttu-id="07c8a-115">Eine oder mehrere zusätzliche `Group Join` -Klauseln zum weiteren Optimieren der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="07c8a-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="07c8a-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="07c8a-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="07c8a-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="07c8a-117">Required.</span></span> <span data-ttu-id="07c8a-118">Bezeichnet die Schlüssel für die Auflistungen verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="07c8a-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="07c8a-119">Verwenden Sie die `Equals` Operator zum Vergleichen von Schlüsseln aus den zu verknüpfenden Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="07c8a-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="07c8a-120">Sie können den Join-Bedingungen kombinieren, mit der `And` Operator, um mehrere Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="07c8a-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="07c8a-121">`key1` aus der Auflistung auf der linken Seite des muss die `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="07c8a-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="07c8a-122">`key2` aus der Auflistung auf der rechten Seite des muss die `Join` Operator.</span><span class="sxs-lookup"><span data-stu-id="07c8a-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="07c8a-123">Die Schlüssel für die Join-Bedingung können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="07c8a-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="07c8a-124">Jedes Schlüssel-Ausdrucks kann jedoch nur die Elemente aus der entsprechenden Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="07c8a-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07c8a-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07c8a-125">Remarks</span></span>  
 <span data-ttu-id="07c8a-126">Die `Join` Klausel Fasst zwei Auflistungen, die basierend auf übereinstimmenden Werte aus den zu verknüpfenden Auflistungen zusammen.</span><span class="sxs-lookup"><span data-stu-id="07c8a-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="07c8a-127">Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung auf der linken Seite des enthalten die `Join` Operator und der Auflistung identifiziert, die der `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="07c8a-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="07c8a-128">Die Abfrage gibt nur Ergebnisse für die die Bedingung, durch angegeben die `Equals` Operator erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="07c8a-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="07c8a-129">Dies ist äquivalent zu einer `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="07c8a-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="07c8a-130">Sie können mehrere `Join` Klauseln in einer Abfrage mindestens zwei Auflistungen in einer einzelnen Auflistung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="07c8a-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="07c8a-131">Sie können eine implizite Verknüpfung zum Kombinieren von Sammlungen ohne Ausführen der `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="07c8a-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="07c8a-132">Zu diesem Zweck fügen Sie mehrere `In` Klauseln in Ihrem `From` Klausel, und geben Sie einen `Where` -Klausel, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="07c8a-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="07c8a-133">Sie können die `Group Join` -Klausel, um Auflistungen in einer einzelnen hierarchischen Auflistung zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="07c8a-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="07c8a-134">Dies ist z. B. eine `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="07c8a-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07c8a-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07c8a-135">Example</span></span>  
 <span data-ttu-id="07c8a-136">Das folgende Codebeispiel führt eine implizite Verknüpfung, um eine Liste von Kunden mit ihrer Bestellungen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="07c8a-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="07c8a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07c8a-137">Example</span></span>  
 <span data-ttu-id="07c8a-138">Im folgenden Codebeispiel wird joins von zwei Auflistungen mithilfe der `Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="07c8a-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]  
  
 <span data-ttu-id="07c8a-139">In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="07c8a-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="07c8a-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07c8a-140">Example</span></span>  
 <span data-ttu-id="07c8a-141">Im folgenden Codebeispiel wird joins von zwei Auflistungen mithilfe der `Join` -Klausel mit zwei Spalten.</span><span class="sxs-lookup"><span data-stu-id="07c8a-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]  
  
 <span data-ttu-id="07c8a-142">Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="07c8a-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="07c8a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07c8a-143">See also</span></span>

- [<span data-ttu-id="07c8a-144">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07c8a-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="07c8a-145">Abfragen</span><span class="sxs-lookup"><span data-stu-id="07c8a-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="07c8a-146">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="07c8a-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="07c8a-147">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="07c8a-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="07c8a-148">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="07c8a-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="07c8a-149">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="07c8a-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
