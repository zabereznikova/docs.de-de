---
title: Vergleichssemantik (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="38674-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38674-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="38674-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="38674-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="38674-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="38674-104">Explicit comparison</span></span>  
 <span data-ttu-id="38674-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="38674-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="38674-106">!=</span><span class="sxs-lookup"><span data-stu-id="38674-106">!=</span></span>  
  
 <span data-ttu-id="38674-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="38674-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="38674-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="38674-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="38674-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="38674-109">IS NULL</span></span>  
  
-   <span data-ttu-id="38674-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="38674-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="38674-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="38674-111">Explicit distinction</span></span>  
 <span data-ttu-id="38674-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="38674-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="38674-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="38674-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="38674-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="38674-114">GROUP BY</span></span>  
  
 <span data-ttu-id="38674-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="38674-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="38674-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="38674-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="38674-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="38674-117">Implicit distinction</span></span>  
 <span data-ttu-id="38674-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="38674-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="38674-119">UNION</span><span class="sxs-lookup"><span data-stu-id="38674-119">UNION</span></span>  
  
-   <span data-ttu-id="38674-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="38674-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="38674-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="38674-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="38674-122">SET</span><span class="sxs-lookup"><span data-stu-id="38674-122">SET</span></span>  
  
-   <span data-ttu-id="38674-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="38674-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="38674-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="38674-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="38674-125">IN</span><span class="sxs-lookup"><span data-stu-id="38674-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="38674-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="38674-126">Supported Combinations</span></span>  
 <span data-ttu-id="38674-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="38674-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="38674-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="38674-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="38674-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="38674-129">**!=**</span></span>|<span data-ttu-id="38674-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="38674-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="38674-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="38674-131">**DISTINCT**</span></span>|<span data-ttu-id="38674-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="38674-132">**UNION**</span></span><br /><br /> <span data-ttu-id="38674-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="38674-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="38674-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="38674-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="38674-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="38674-135">**SET**</span></span><br /><br /> <span data-ttu-id="38674-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="38674-136">**OVERLAPS**</span></span>|<span data-ttu-id="38674-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="38674-137">**IN**</span></span>|<span data-ttu-id="38674-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="38674-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="38674-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="38674-139">**>   >=**</span></span>|<span data-ttu-id="38674-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="38674-140">**ORDER BY**</span></span>|<span data-ttu-id="38674-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="38674-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="38674-142">**IST UNGLEICH NULL**</span><span class="sxs-lookup"><span data-stu-id="38674-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="38674-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="38674-143">Entity type</span></span>|<span data-ttu-id="38674-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="38674-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="38674-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38674-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="38674-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38674-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="38674-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38674-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="38674-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="38674-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="38674-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="38674-151">Complex type</span></span>|<span data-ttu-id="38674-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38674-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="38674-159">Row</span></span>|<span data-ttu-id="38674-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38674-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="38674-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38674-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="38674-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38674-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="38674-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38674-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="38674-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38674-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="38674-167">Primitive type</span></span>|<span data-ttu-id="38674-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-168">Provider-specific</span></span>|<span data-ttu-id="38674-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-169">Provider-specific</span></span>|<span data-ttu-id="38674-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-170">Provider-specific</span></span>|<span data-ttu-id="38674-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-171">Provider-specific</span></span>|<span data-ttu-id="38674-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-172">Provider-specific</span></span>|<span data-ttu-id="38674-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-173">Provider-specific</span></span>|<span data-ttu-id="38674-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="38674-174">Provider-specific</span></span>|  
|<span data-ttu-id="38674-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="38674-175">Multiset</span></span>|<span data-ttu-id="38674-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38674-183">Ref</span><span class="sxs-lookup"><span data-stu-id="38674-183">Ref</span></span>|<span data-ttu-id="38674-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38674-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="38674-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38674-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="38674-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38674-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="38674-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38674-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="38674-188">Throw</span><span class="sxs-lookup"><span data-stu-id="38674-188">Throw</span></span>|<span data-ttu-id="38674-189">Throw</span><span class="sxs-lookup"><span data-stu-id="38674-189">Throw</span></span>|<span data-ttu-id="38674-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38674-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="38674-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="38674-191">Association</span></span><br /><br /> <span data-ttu-id="38674-192">Typ</span><span class="sxs-lookup"><span data-stu-id="38674-192">type</span></span>|<span data-ttu-id="38674-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-194">Throw</span><span class="sxs-lookup"><span data-stu-id="38674-194">Throw</span></span>|<span data-ttu-id="38674-195">Throw</span><span class="sxs-lookup"><span data-stu-id="38674-195">Throw</span></span>|<span data-ttu-id="38674-196">Throw</span><span class="sxs-lookup"><span data-stu-id="38674-196">Throw</span></span>|<span data-ttu-id="38674-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="38674-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38674-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="38674-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="38674-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="38674-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="38674-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="38674-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="38674-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="38674-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="38674-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="38674-204"><sup>2</sup>Eigenschaften komplexer Typen werden vor dem Senden in den Speicher, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="38674-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="38674-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="38674-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="38674-206"><sup>3</sup>die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne den Anbieter/Speicher Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="38674-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="38674-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="38674-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="38674-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="38674-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="38674-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (einschließlich des Namens der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="38674-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38674-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38674-210">See Also</span></span>  
 [<span data-ttu-id="38674-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="38674-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
