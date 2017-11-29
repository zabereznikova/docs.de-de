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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1fd1c21fc4f156bfe7a5abf9f76bd341e2d0f10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="636b5-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="636b5-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="636b5-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="636b5-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="636b5-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="636b5-104">Explicit comparison</span></span>  
 <span data-ttu-id="636b5-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="636b5-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="636b5-106">!=</span><span class="sxs-lookup"><span data-stu-id="636b5-106">!=</span></span>  
  
 <span data-ttu-id="636b5-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="636b5-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="636b5-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="636b5-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="636b5-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="636b5-109">IS NULL</span></span>  
  
-   <span data-ttu-id="636b5-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="636b5-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="636b5-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="636b5-111">Explicit distinction</span></span>  
 <span data-ttu-id="636b5-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="636b5-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="636b5-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="636b5-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="636b5-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="636b5-114">GROUP BY</span></span>  
  
 <span data-ttu-id="636b5-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="636b5-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="636b5-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="636b5-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="636b5-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="636b5-117">Implicit distinction</span></span>  
 <span data-ttu-id="636b5-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="636b5-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="636b5-119">UNION</span><span class="sxs-lookup"><span data-stu-id="636b5-119">UNION</span></span>  
  
-   <span data-ttu-id="636b5-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="636b5-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="636b5-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="636b5-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="636b5-122">SET</span><span class="sxs-lookup"><span data-stu-id="636b5-122">SET</span></span>  
  
-   <span data-ttu-id="636b5-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="636b5-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="636b5-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="636b5-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="636b5-125">IN</span><span class="sxs-lookup"><span data-stu-id="636b5-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="636b5-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="636b5-126">Supported Combinations</span></span>  
 <span data-ttu-id="636b5-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="636b5-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="636b5-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="636b5-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="636b5-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="636b5-129">**!=**</span></span>|<span data-ttu-id="636b5-130">**GRUPPIEREN NACH**</span><span class="sxs-lookup"><span data-stu-id="636b5-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="636b5-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="636b5-131">**DISTINCT**</span></span>|<span data-ttu-id="636b5-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="636b5-132">**UNION**</span></span><br /><br /> <span data-ttu-id="636b5-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="636b5-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="636b5-134">**AUSNAHME:**</span><span class="sxs-lookup"><span data-stu-id="636b5-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="636b5-135">**FESTLEGEN**</span><span class="sxs-lookup"><span data-stu-id="636b5-135">**SET**</span></span><br /><br /> <span data-ttu-id="636b5-136">**(ÜBERLAPPUNGEN)**</span><span class="sxs-lookup"><span data-stu-id="636b5-136">**OVERLAPS**</span></span>|<span data-ttu-id="636b5-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="636b5-137">**IN**</span></span>|<span data-ttu-id="636b5-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="636b5-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="636b5-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="636b5-139">**>   >=**</span></span>|<span data-ttu-id="636b5-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="636b5-140">**ORDER BY**</span></span>|<span data-ttu-id="636b5-141">**IST NULL.**</span><span class="sxs-lookup"><span data-stu-id="636b5-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="636b5-142">**IST UNGLEICH NULL**</span><span class="sxs-lookup"><span data-stu-id="636b5-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="636b5-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="636b5-143">Entity type</span></span>|<span data-ttu-id="636b5-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="636b5-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="636b5-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="636b5-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="636b5-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="636b5-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="636b5-151">Complex type</span></span>|<span data-ttu-id="636b5-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="636b5-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="636b5-159">Row</span></span>|<span data-ttu-id="636b5-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="636b5-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="636b5-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="636b5-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="636b5-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="636b5-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="636b5-167">Primitive type</span></span>|<span data-ttu-id="636b5-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-168">Provider-specific</span></span>|<span data-ttu-id="636b5-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-169">Provider-specific</span></span>|<span data-ttu-id="636b5-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-170">Provider-specific</span></span>|<span data-ttu-id="636b5-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-171">Provider-specific</span></span>|<span data-ttu-id="636b5-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-172">Provider-specific</span></span>|<span data-ttu-id="636b5-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-173">Provider-specific</span></span>|<span data-ttu-id="636b5-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="636b5-174">Provider-specific</span></span>|  
|<span data-ttu-id="636b5-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="636b5-175">Multiset</span></span>|<span data-ttu-id="636b5-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="636b5-183">Ref</span><span class="sxs-lookup"><span data-stu-id="636b5-183">Ref</span></span>|<span data-ttu-id="636b5-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="636b5-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="636b5-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="636b5-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="636b5-188">Throw</span><span class="sxs-lookup"><span data-stu-id="636b5-188">Throw</span></span>|<span data-ttu-id="636b5-189">Throw</span><span class="sxs-lookup"><span data-stu-id="636b5-189">Throw</span></span>|<span data-ttu-id="636b5-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="636b5-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="636b5-191">Association</span></span><br /><br /> <span data-ttu-id="636b5-192">Typ</span><span class="sxs-lookup"><span data-stu-id="636b5-192">type</span></span>|<span data-ttu-id="636b5-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-194">Throw</span><span class="sxs-lookup"><span data-stu-id="636b5-194">Throw</span></span>|<span data-ttu-id="636b5-195">Throw</span><span class="sxs-lookup"><span data-stu-id="636b5-195">Throw</span></span>|<span data-ttu-id="636b5-196">Throw</span><span class="sxs-lookup"><span data-stu-id="636b5-196">Throw</span></span>|<span data-ttu-id="636b5-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="636b5-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="636b5-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="636b5-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="636b5-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="636b5-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="636b5-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="636b5-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="636b5-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="636b5-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="636b5-204"><sup>2</sup>Eigenschaften komplexer Typen werden vor dem Senden in den Speicher, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="636b5-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="636b5-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="636b5-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="636b5-206"><sup>3</sup>die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne den Anbieter/Speicher Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="636b5-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="636b5-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="636b5-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="636b5-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="636b5-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="636b5-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (einschließlich des Namens der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="636b5-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636b5-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="636b5-210">See Also</span></span>  
 [<span data-ttu-id="636b5-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="636b5-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
