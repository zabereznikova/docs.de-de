---
title: Group By-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 5fce4f818e22373de7f1b37b941fd88155f3a33f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359889"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="9b95e-102">GROUP BY-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b95e-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="9b95e-103">Gruppiert die Elemente eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="9b95e-103">Groups the elements of a query result.</span></span> <span data-ttu-id="9b95e-104">Kann auch verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="9b95e-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="9b95e-105">Der Gruppierungsvorgang basiert auf einem oder mehreren Schlüssel(n).</span><span class="sxs-lookup"><span data-stu-id="9b95e-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b95e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b95e-106">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="9b95e-107">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9b95e-107">Parts</span></span>  
  
- <span data-ttu-id="9b95e-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="9b95e-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="9b95e-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b95e-109">Optional.</span></span> <span data-ttu-id="9b95e-110">Mindestens eins der Felder der einen oder mehreren Abfragevariablen, die explizit die in das gruppierte Ergebnis aufzunehmenden Felder bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="9b95e-111">Wenn keine Felder angegeben werden, sind alle Felder der Abfragevariablen im gruppierten Ergebnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="9b95e-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="9b95e-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b95e-112">Required.</span></span> <span data-ttu-id="9b95e-113">Ein Ausdruck, der den Schlüssel zum Bestimmen der Elementgruppen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9b95e-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="9b95e-114">Zum Angeben eines zusammengesetzten Schlüssels können mehrere Schlüssel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b95e-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="9b95e-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b95e-115">Optional.</span></span> <span data-ttu-id="9b95e-116">Mindestens ein zusätzlicher Schlüssel, die mit `keyExp1` kombiniert werden, um einen zusammengesetzten Schlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="9b95e-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b95e-117">Required.</span></span> <span data-ttu-id="9b95e-118">Mindestens ein Ausdruck, der angibt, wie die Gruppen aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="9b95e-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="9b95e-119">Zum Angeben eines Membernamens für die gruppierten Ergebnisse können Sie das Schlüsselwort `Group` in einer der folgenden Formen verwenden:</span><span class="sxs-lookup"><span data-stu-id="9b95e-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="9b95e-120">Oder</span><span class="sxs-lookup"><span data-stu-id="9b95e-120">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="9b95e-121">Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b95e-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b95e-122">Remarks</span></span>  
 <span data-ttu-id="9b95e-123">Sie können die `Group By` -Klausel verwenden, um die Ergebnisse einer Abfrage in Gruppen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="9b95e-124">Die Gruppierung erfolgt auf der Basis eines Schlüssels oder eines zusammengesetzten Schlüssels, der aus mehreren Schlüsseln besteht.</span><span class="sxs-lookup"><span data-stu-id="9b95e-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="9b95e-125">Elemente, die übereinstimmenden Schlüsselwerten zugeordnet sind werden in die gleiche Gruppe aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="9b95e-126">Sie verwenden den `aggregateList` -Parameter der `Into` -Klausel und das `Group` -Schlüsselwort, um den Membernamen zu bezeichnen, der zum Verweisen auf die Gruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b95e-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="9b95e-127">Ferner kann die `Into` -Klausel Aggregatfunktionen beinhalten, um Werte für die gruppierten Elemente zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="9b95e-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="9b95e-128">Eine Liste der standardmäßigen Aggregatfunktionen finden Sie unter [Aggregate Clause](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9b95e-128">For a list of standard aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b95e-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b95e-129">Example</span></span>  
 <span data-ttu-id="9b95e-130">Im folgenden Codebeispiel wird eine Liste von Kunden basierend auf Ihrem Standort (Land/Region) gruppiert und die Anzahl der Kunden in jeder Gruppe bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9b95e-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="9b95e-131">Die Ergebnisse werden nach Land/Region-Name geordnet.</span><span class="sxs-lookup"><span data-stu-id="9b95e-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="9b95e-132">Die gruppierten Ergebnisse sind nach Städtenamen geordnet.</span><span class="sxs-lookup"><span data-stu-id="9b95e-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="9b95e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b95e-133">See also</span></span>

- [<span data-ttu-id="9b95e-134">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b95e-134">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9b95e-135">Abfragen</span><span class="sxs-lookup"><span data-stu-id="9b95e-135">Queries</span></span>](index.md)
- [<span data-ttu-id="9b95e-136">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="9b95e-136">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9b95e-137">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="9b95e-137">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="9b95e-138">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="9b95e-138">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="9b95e-139">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="9b95e-139">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="9b95e-140">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="9b95e-140">Group Join Clause</span></span>](group-join-clause.md)
