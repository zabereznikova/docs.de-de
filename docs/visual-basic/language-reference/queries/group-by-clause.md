---
title: Group By-Klausel (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a27e2f15e61456b2e7ac0ede81c66cdb4e8fd612
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="acff0-102">GROUP BY-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acff0-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="acff0-103">Gruppiert die Elemente eines Abfrageergebnisses.</span><span class="sxs-lookup"><span data-stu-id="acff0-103">Groups the elements of a query result.</span></span> <span data-ttu-id="acff0-104">Kann auch verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="acff0-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="acff0-105">Der Gruppierungsvorgang basiert auf einem oder mehreren Schlüssel(n).</span><span class="sxs-lookup"><span data-stu-id="acff0-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acff0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="acff0-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="acff0-107">Teile</span><span class="sxs-lookup"><span data-stu-id="acff0-107">Parts</span></span>  
  
-   <span data-ttu-id="acff0-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="acff0-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="acff0-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="acff0-109">Optional.</span></span> <span data-ttu-id="acff0-110">Mindestens eins der Felder der einen oder mehreren Abfragevariablen, die explizit die in das gruppierte Ergebnis aufzunehmenden Felder bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="acff0-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="acff0-111">Wenn keine Felder angegeben werden, sind alle Felder der Abfragevariablen im gruppierten Ergebnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="acff0-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="acff0-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="acff0-112">Required.</span></span> <span data-ttu-id="acff0-113">Ein Ausdruck, der den Schlüssel zum Bestimmen der Elementgruppen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="acff0-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="acff0-114">Zum Angeben eines zusammengesetzten Schlüssels können mehrere Schlüssel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="acff0-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="acff0-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="acff0-115">Optional.</span></span> <span data-ttu-id="acff0-116">Mindestens ein zusätzlicher Schlüssel, die mit `keyExp1` kombiniert werden, um einen zusammengesetzten Schlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="acff0-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="acff0-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="acff0-117">Required.</span></span> <span data-ttu-id="acff0-118">Mindestens ein Ausdruck, der angibt, wie die Gruppen aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="acff0-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="acff0-119">Zum Angeben eines Membernamens für die gruppierten Ergebnisse können Sie das Schlüsselwort `Group` in einer der folgenden Formen verwenden:</span><span class="sxs-lookup"><span data-stu-id="acff0-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="acff0-120">- oder -</span><span class="sxs-lookup"><span data-stu-id="acff0-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="acff0-121">Sie können auch Aggregatfunktionen einschließen, die auf die Gruppe angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acff0-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acff0-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acff0-122">Remarks</span></span>  
 <span data-ttu-id="acff0-123">Sie können die `Group By` -Klausel verwenden, um die Ergebnisse einer Abfrage in Gruppen aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="acff0-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="acff0-124">Die Gruppierung erfolgt auf der Basis eines Schlüssels oder eines zusammengesetzten Schlüssels, der aus mehreren Schlüsseln besteht.</span><span class="sxs-lookup"><span data-stu-id="acff0-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="acff0-125">Elemente, die übereinstimmenden Schlüsselwerten zugeordnet sind werden in die gleiche Gruppe aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="acff0-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="acff0-126">Sie verwenden den `aggregateList` -Parameter der `Into` -Klausel und das `Group` -Schlüsselwort, um den Membernamen zu bezeichnen, der zum Verweisen auf die Gruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="acff0-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="acff0-127">Ferner kann die `Into` -Klausel Aggregatfunktionen beinhalten, um Werte für die gruppierten Elemente zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="acff0-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="acff0-128">Eine Liste der standard-Aggregatfunktionen, finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="acff0-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acff0-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acff0-129">Example</span></span>  
 <span data-ttu-id="acff0-130">Im folgenden Codebeispiel wird eine Liste von Kunden basierend auf ihrem Standort (Land) gruppiert und die Anzahl der Kunden in jeder Gruppe angegeben.</span><span class="sxs-lookup"><span data-stu-id="acff0-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="acff0-131">Die Ergebnisse werden nach Ländernamen geordnet.</span><span class="sxs-lookup"><span data-stu-id="acff0-131">The results are ordered by country name.</span></span> <span data-ttu-id="acff0-132">Die gruppierten Ergebnisse sind nach Städtenamen geordnet.</span><span class="sxs-lookup"><span data-stu-id="acff0-132">The grouped results are ordered by city name.</span></span>  
  
 <span data-ttu-id="acff0-133">[!code-vb[VbSimpleQuerySamples&#11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="acff0-133">[!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acff0-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acff0-134">See Also</span></span>  
 <span data-ttu-id="acff0-135">[Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="acff0-136"> [Abfragen](../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-136"> [Queries](../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="acff0-137"> [SELECT-Klausel](../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-137"> [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="acff0-138"> [FROM-Klausel](../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-138"> [From Clause](../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="acff0-139"> [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-139"> [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="acff0-140"> [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="acff0-140"> [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="acff0-141"> [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md)</span><span class="sxs-lookup"><span data-stu-id="acff0-141"> [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)</span></span>
