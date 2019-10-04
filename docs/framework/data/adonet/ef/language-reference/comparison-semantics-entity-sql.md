---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833944"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="957f7-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="957f7-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="957f7-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="957f7-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="957f7-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="957f7-104">Explicit comparison</span></span>  
 <span data-ttu-id="957f7-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="957f7-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="957f7-106">!=</span><span class="sxs-lookup"><span data-stu-id="957f7-106">!=</span></span>  
  
 <span data-ttu-id="957f7-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="957f7-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="957f7-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="957f7-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="957f7-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="957f7-109">IS NULL</span></span>  
  
- <span data-ttu-id="957f7-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="957f7-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="957f7-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="957f7-111">Explicit distinction</span></span>  
 <span data-ttu-id="957f7-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="957f7-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="957f7-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="957f7-113">DISTINCT</span></span>  
  
- <span data-ttu-id="957f7-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="957f7-114">GROUP BY</span></span>  
  
 <span data-ttu-id="957f7-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="957f7-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="957f7-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="957f7-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="957f7-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="957f7-117">Implicit distinction</span></span>  
 <span data-ttu-id="957f7-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="957f7-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="957f7-119">UNION</span><span class="sxs-lookup"><span data-stu-id="957f7-119">UNION</span></span>  
  
- <span data-ttu-id="957f7-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="957f7-120">INTERSECT</span></span>  
  
- <span data-ttu-id="957f7-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="957f7-121">EXCEPT</span></span>  
  
- <span data-ttu-id="957f7-122">SET</span><span class="sxs-lookup"><span data-stu-id="957f7-122">SET</span></span>  
  
- <span data-ttu-id="957f7-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="957f7-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="957f7-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="957f7-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="957f7-125">IN</span><span class="sxs-lookup"><span data-stu-id="957f7-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="957f7-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="957f7-126">Supported Combinations</span></span>  
 <span data-ttu-id="957f7-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="957f7-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="957f7-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="957f7-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="957f7-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="957f7-129">**!=**</span></span>|<span data-ttu-id="957f7-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="957f7-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="957f7-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="957f7-131">**DISTINCT**</span></span>|<span data-ttu-id="957f7-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="957f7-132">**UNION**</span></span><br /><br /> <span data-ttu-id="957f7-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="957f7-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="957f7-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="957f7-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="957f7-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="957f7-135">**SET**</span></span><br /><br /> <span data-ttu-id="957f7-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="957f7-136">**OVERLAPS**</span></span>|<span data-ttu-id="957f7-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="957f7-137">**IN**</span></span>|<span data-ttu-id="957f7-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="957f7-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="957f7-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="957f7-139">**>   >=**</span></span>|<span data-ttu-id="957f7-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="957f7-140">**ORDER BY**</span></span>|<span data-ttu-id="957f7-141">**IST NULL**</span><span class="sxs-lookup"><span data-stu-id="957f7-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="957f7-142">**IST NICHT NULL**</span><span class="sxs-lookup"><span data-stu-id="957f7-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="957f7-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="957f7-143">Entity type</span></span>|<span data-ttu-id="957f7-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="957f7-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="957f7-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="957f7-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="957f7-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="957f7-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="957f7-151">Complex type</span></span>|<span data-ttu-id="957f7-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="957f7-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="957f7-159">Row</span></span>|<span data-ttu-id="957f7-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="957f7-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="957f7-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="957f7-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="957f7-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="957f7-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="957f7-167">Primitive type</span></span>|<span data-ttu-id="957f7-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-168">Provider-specific</span></span>|<span data-ttu-id="957f7-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-169">Provider-specific</span></span>|<span data-ttu-id="957f7-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-170">Provider-specific</span></span>|<span data-ttu-id="957f7-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-171">Provider-specific</span></span>|<span data-ttu-id="957f7-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-172">Provider-specific</span></span>|<span data-ttu-id="957f7-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-173">Provider-specific</span></span>|<span data-ttu-id="957f7-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="957f7-174">Provider-specific</span></span>|  
|<span data-ttu-id="957f7-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="957f7-175">Multiset</span></span>|<span data-ttu-id="957f7-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="957f7-183">Ref</span><span class="sxs-lookup"><span data-stu-id="957f7-183">Ref</span></span>|<span data-ttu-id="957f7-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="957f7-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="957f7-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="957f7-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="957f7-188">Throw</span><span class="sxs-lookup"><span data-stu-id="957f7-188">Throw</span></span>|<span data-ttu-id="957f7-189">Throw</span><span class="sxs-lookup"><span data-stu-id="957f7-189">Throw</span></span>|<span data-ttu-id="957f7-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="957f7-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="957f7-191">Association</span></span><br /><br /> <span data-ttu-id="957f7-192">Typ</span><span class="sxs-lookup"><span data-stu-id="957f7-192">type</span></span>|<span data-ttu-id="957f7-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-194">Throw</span><span class="sxs-lookup"><span data-stu-id="957f7-194">Throw</span></span>|<span data-ttu-id="957f7-195">Throw</span><span class="sxs-lookup"><span data-stu-id="957f7-195">Throw</span></span>|<span data-ttu-id="957f7-196">Throw</span><span class="sxs-lookup"><span data-stu-id="957f7-196">Throw</span></span>|<span data-ttu-id="957f7-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="957f7-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="957f7-200"><sup>1</sup> Die Verweise der angegebenen Entitätstyp Instanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="957f7-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="957f7-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="957f7-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="957f7-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="957f7-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="957f7-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="957f7-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="957f7-204"><sup>2</sup> Eigenschaften komplexer Typen werden vereinfacht, bevor Sie an den Speicher gesendet werden, sodass Sie vergleichbar sind (solange alle Eigenschaften vergleichbar sind).</span><span class="sxs-lookup"><span data-stu-id="957f7-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="957f7-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="957f7-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="957f7-206"><sup>3</sup> Die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine sinnvolle Ausnahme aus, ohne den Anbieter bzw. den Speicher einzubinden.</span><span class="sxs-lookup"><span data-stu-id="957f7-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="957f7-207"><sup>4</sup> Es wurde versucht, alle Eigenschaften zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="957f7-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="957f7-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="957f7-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="957f7-209"><sup>5</sup> Alle einzelnen Elemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und alle Schlüsseleigenschaften des Entitäts Typs ein).</span><span class="sxs-lookup"><span data-stu-id="957f7-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957f7-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="957f7-210">See also</span></span>

- [<span data-ttu-id="957f7-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="957f7-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
