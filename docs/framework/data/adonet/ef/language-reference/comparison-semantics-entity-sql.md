---
title: Vergleichssemantik (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c6d22b72e05e6293a7fd3bcf7ddfba6e116e441f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="279b8-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="279b8-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="279b8-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="279b8-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="279b8-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="279b8-104">Explicit comparison</span></span>  
 <span data-ttu-id="279b8-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="279b8-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="279b8-106">!=</span><span class="sxs-lookup"><span data-stu-id="279b8-106">!=</span></span>  
  
 <span data-ttu-id="279b8-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="279b8-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="279b8-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="279b8-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="279b8-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="279b8-109">IS NULL</span></span>  
  
-   <span data-ttu-id="279b8-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="279b8-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="279b8-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="279b8-111">Explicit distinction</span></span>  
 <span data-ttu-id="279b8-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="279b8-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="279b8-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="279b8-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="279b8-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="279b8-114">GROUP BY</span></span>  
  
 <span data-ttu-id="279b8-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="279b8-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="279b8-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="279b8-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="279b8-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="279b8-117">Implicit distinction</span></span>  
 <span data-ttu-id="279b8-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="279b8-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="279b8-119">UNION</span><span class="sxs-lookup"><span data-stu-id="279b8-119">UNION</span></span>  
  
-   <span data-ttu-id="279b8-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="279b8-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="279b8-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="279b8-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="279b8-122">SET</span><span class="sxs-lookup"><span data-stu-id="279b8-122">SET</span></span>  
  
-   <span data-ttu-id="279b8-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="279b8-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="279b8-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="279b8-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="279b8-125">IN</span><span class="sxs-lookup"><span data-stu-id="279b8-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="279b8-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="279b8-126">Supported Combinations</span></span>  
 <span data-ttu-id="279b8-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="279b8-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="279b8-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="279b8-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="279b8-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="279b8-129">**!=**</span></span>|<span data-ttu-id="279b8-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="279b8-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="279b8-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="279b8-131">**DISTINCT**</span></span>|<span data-ttu-id="279b8-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="279b8-132">**UNION**</span></span><br /><br /> <span data-ttu-id="279b8-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="279b8-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="279b8-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="279b8-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="279b8-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="279b8-135">**SET**</span></span><br /><br /> <span data-ttu-id="279b8-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="279b8-136">**OVERLAPS**</span></span>|<span data-ttu-id="279b8-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="279b8-137">**IN**</span></span>|<span data-ttu-id="279b8-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="279b8-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="279b8-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="279b8-139">**>   >=**</span></span>|<span data-ttu-id="279b8-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="279b8-140">**ORDER BY**</span></span>|<span data-ttu-id="279b8-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="279b8-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="279b8-142">**IST UNGLEICH NULL**</span><span class="sxs-lookup"><span data-stu-id="279b8-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="279b8-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="279b8-143">Entity type</span></span>|<span data-ttu-id="279b8-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="279b8-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="279b8-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="279b8-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="279b8-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="279b8-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="279b8-151">Complex type</span></span>|<span data-ttu-id="279b8-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="279b8-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="279b8-159">Row</span></span>|<span data-ttu-id="279b8-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="279b8-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="279b8-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="279b8-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="279b8-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="279b8-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="279b8-167">Primitive type</span></span>|<span data-ttu-id="279b8-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-168">Provider-specific</span></span>|<span data-ttu-id="279b8-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-169">Provider-specific</span></span>|<span data-ttu-id="279b8-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-170">Provider-specific</span></span>|<span data-ttu-id="279b8-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-171">Provider-specific</span></span>|<span data-ttu-id="279b8-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-172">Provider-specific</span></span>|<span data-ttu-id="279b8-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-173">Provider-specific</span></span>|<span data-ttu-id="279b8-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="279b8-174">Provider-specific</span></span>|  
|<span data-ttu-id="279b8-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="279b8-175">Multiset</span></span>|<span data-ttu-id="279b8-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="279b8-183">Ref</span><span class="sxs-lookup"><span data-stu-id="279b8-183">Ref</span></span>|<span data-ttu-id="279b8-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="279b8-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="279b8-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="279b8-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="279b8-188">Throw</span><span class="sxs-lookup"><span data-stu-id="279b8-188">Throw</span></span>|<span data-ttu-id="279b8-189">Throw</span><span class="sxs-lookup"><span data-stu-id="279b8-189">Throw</span></span>|<span data-ttu-id="279b8-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="279b8-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="279b8-191">Association</span></span><br /><br /> <span data-ttu-id="279b8-192">Typ</span><span class="sxs-lookup"><span data-stu-id="279b8-192">type</span></span>|<span data-ttu-id="279b8-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-194">Throw</span><span class="sxs-lookup"><span data-stu-id="279b8-194">Throw</span></span>|<span data-ttu-id="279b8-195">Throw</span><span class="sxs-lookup"><span data-stu-id="279b8-195">Throw</span></span>|<span data-ttu-id="279b8-196">Throw</span><span class="sxs-lookup"><span data-stu-id="279b8-196">Throw</span></span>|<span data-ttu-id="279b8-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="279b8-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="279b8-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="279b8-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="279b8-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="279b8-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="279b8-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="279b8-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="279b8-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="279b8-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="279b8-204"><sup>2</sup>Eigenschaften komplexer Typen werden vor dem Senden in den Speicher, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="279b8-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="279b8-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="279b8-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="279b8-206"><sup>3</sup>die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne den Anbieter/Speicher Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="279b8-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="279b8-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="279b8-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="279b8-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="279b8-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="279b8-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (einschließlich des Namens der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="279b8-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279b8-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="279b8-210">See Also</span></span>  
 [<span data-ttu-id="279b8-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="279b8-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
