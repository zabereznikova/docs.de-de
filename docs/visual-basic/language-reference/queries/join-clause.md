---
title: Join-Klausel
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
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359773"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="2c4b3-102">Join-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c4b3-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="2c4b3-103">Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="2c4b3-104">Der Joinvorgang basiert auf übereinstimmenden Schlüsseln und verwendet den- `Equals` Operator.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c4b3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c4b3-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="2c4b3-106">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="2c4b3-106">Parts</span></span>

<span data-ttu-id="2c4b3-107">`element` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-107">`element` Required.</span></span> <span data-ttu-id="2c4b3-108">Die Steuerelement Variable für die Auflistung, die verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="2c4b3-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-109">Required.</span></span> <span data-ttu-id="2c4b3-110">Die Auflistung, die mit der auf der linken Seite des Operators identifizierten Auflistung kombiniert werden soll `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="2c4b3-111">Eine- `Join` Klausel kann in einer anderen- `Join` Klausel oder in einer- `Group Join` Klausel eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="2c4b3-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-112">Optional.</span></span> <span data-ttu-id="2c4b3-113">Eine oder mehrere zusätzliche `Join` Klauseln, um die Abfrage weiter zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="2c4b3-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-114">Optional.</span></span> <span data-ttu-id="2c4b3-115">Eine oder mehrere zusätzliche `Group Join` Klauseln, um die Abfrage weiter zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="2c4b3-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="2c4b3-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="2c4b3-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-117">Required.</span></span> <span data-ttu-id="2c4b3-118">Identifiziert Schlüssel für die Auflistungen, die verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="2c4b3-119">Sie müssen den- `Equals` Operator verwenden, um Schlüssel aus den verbundenen Sammlungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="2c4b3-120">Joinbedingungen können mithilfe des-Operators kombiniert werden `And` , um mehrere Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="2c4b3-121">`key1`muss sich auf der linken Seite des Operators aus der Auflistung befinden `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="2c4b3-122">`key2`muss von der Auflistung auf der rechten Seite des Operators sein `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="2c4b3-123">Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="2c4b3-124">Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c4b3-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2c4b3-125">Remarks</span></span>

<span data-ttu-id="2c4b3-126">Die- `Join` Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="2c4b3-127">Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung enthalten, die auf der linken Seite des Operators identifiziert wird, `Join` und die in der-Klausel identifizierte Auflistung `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="2c4b3-128">Die Abfrage gibt nur Ergebnisse zurück, für die die vom Operator angegebene Bedingung `Equals` erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="2c4b3-129">Dies entspricht einem `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="2c4b3-130">Sie können mehrere `Join` Klauseln in einer Abfrage verwenden, um zwei oder mehr Auflistungen in einer einzelnen Auflistung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="2c4b3-131">Sie können einen impliziten Join ausführen, um Auflistungen ohne die-Klausel zu kombinieren `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="2c4b3-132">Fügen Sie zu diesem Zweck mehrere `In` -Klauseln in die `From` -Klausel ein, und geben Sie eine- `Where` Klausel an, die die Schlüssel identifiziert, die Sie für den Join verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="2c4b3-133">Sie können die- `Group Join` Klausel verwenden, um Sammlungen in einer einzelnen hierarchischen Auflistung zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="2c4b3-134">Dies ist wie ein `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="2c4b3-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-135">Example</span></span>

<span data-ttu-id="2c4b3-136">Im folgenden Codebeispiel wird ein impliziter Join durchführt, um eine Liste von Kunden mit Ihren Aufträgen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="2c4b3-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-137">Example</span></span>

<span data-ttu-id="2c4b3-138">Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der-Klausel miteinander verbunden `Join` .</span><span class="sxs-lookup"><span data-stu-id="2c4b3-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="2c4b3-139">In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="2c4b3-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="2c4b3-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-140">Example</span></span>

<span data-ttu-id="2c4b3-141">Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der- `Join` Klausel mit zwei Schlüssel Spalten verbunden.</span><span class="sxs-lookup"><span data-stu-id="2c4b3-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="2c4b3-142">Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="2c4b3-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="2c4b3-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c4b3-143">See also</span></span>

- [<span data-ttu-id="2c4b3-144">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c4b3-144">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2c4b3-145">Abfragen</span><span class="sxs-lookup"><span data-stu-id="2c4b3-145">Queries</span></span>](index.md)
- [<span data-ttu-id="2c4b3-146">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-146">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="2c4b3-147">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-147">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="2c4b3-148">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-148">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="2c4b3-149">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="2c4b3-149">Where Clause</span></span>](where-clause.md)
