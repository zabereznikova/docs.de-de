---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 9a36fcc4476c25d64fed670e857f339fb20043d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197832"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="e123f-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e123f-102">Comparison Semantics (Entity SQL)</span></span>

<span data-ttu-id="e123f-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="e123f-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="e123f-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="e123f-104">Explicit comparison</span></span>  

 <span data-ttu-id="e123f-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="e123f-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="e123f-106">!=</span><span class="sxs-lookup"><span data-stu-id="e123f-106">!=</span></span>  
  
 <span data-ttu-id="e123f-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="e123f-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="e123f-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="e123f-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="e123f-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="e123f-109">IS NULL</span></span>  
  
- <span data-ttu-id="e123f-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e123f-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="e123f-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="e123f-111">Explicit distinction</span></span>  

 <span data-ttu-id="e123f-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="e123f-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="e123f-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="e123f-113">DISTINCT</span></span>  
  
- <span data-ttu-id="e123f-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="e123f-114">GROUP BY</span></span>  
  
 <span data-ttu-id="e123f-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="e123f-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="e123f-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="e123f-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="e123f-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="e123f-117">Implicit distinction</span></span>  

 <span data-ttu-id="e123f-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="e123f-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="e123f-119">UNION</span><span class="sxs-lookup"><span data-stu-id="e123f-119">UNION</span></span>  
  
- <span data-ttu-id="e123f-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="e123f-120">INTERSECT</span></span>  
  
- <span data-ttu-id="e123f-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="e123f-121">EXCEPT</span></span>  
  
- <span data-ttu-id="e123f-122">SET</span><span class="sxs-lookup"><span data-stu-id="e123f-122">SET</span></span>  
  
- <span data-ttu-id="e123f-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="e123f-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="e123f-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="e123f-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="e123f-125">IN</span><span class="sxs-lookup"><span data-stu-id="e123f-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="e123f-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="e123f-126">Supported Combinations</span></span>  

 <span data-ttu-id="e123f-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e123f-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="e123f-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e123f-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="e123f-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="e123f-129">**!=**</span></span>|<span data-ttu-id="e123f-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="e123f-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="e123f-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="e123f-131">**DISTINCT**</span></span>|<span data-ttu-id="e123f-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="e123f-132">**UNION**</span></span><br /><br /> <span data-ttu-id="e123f-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="e123f-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="e123f-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="e123f-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="e123f-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="e123f-135">**SET**</span></span><br /><br /> <span data-ttu-id="e123f-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="e123f-136">**OVERLAPS**</span></span>|<span data-ttu-id="e123f-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="e123f-137">**IN**</span></span>|<span data-ttu-id="e123f-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="e123f-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="e123f-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="e123f-139">**>   >=**</span></span>|<span data-ttu-id="e123f-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="e123f-140">**ORDER BY**</span></span>|<span data-ttu-id="e123f-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="e123f-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="e123f-142">**ist nicht NULL**</span><span class="sxs-lookup"><span data-stu-id="e123f-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="e123f-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="e123f-143">Entity type</span></span>|<span data-ttu-id="e123f-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="e123f-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="e123f-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="e123f-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="e123f-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="e123f-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="e123f-151">Complex type</span></span>|<span data-ttu-id="e123f-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e123f-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="e123f-159">Row</span></span>|<span data-ttu-id="e123f-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="e123f-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="e123f-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="e123f-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="e123f-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e123f-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="e123f-167">Primitive type</span></span>|<span data-ttu-id="e123f-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-168">Provider-specific</span></span>|<span data-ttu-id="e123f-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-169">Provider-specific</span></span>|<span data-ttu-id="e123f-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-170">Provider-specific</span></span>|<span data-ttu-id="e123f-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-171">Provider-specific</span></span>|<span data-ttu-id="e123f-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-172">Provider-specific</span></span>|<span data-ttu-id="e123f-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-173">Provider-specific</span></span>|<span data-ttu-id="e123f-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="e123f-174">Provider-specific</span></span>|  
|<span data-ttu-id="e123f-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="e123f-175">Multiset</span></span>|<span data-ttu-id="e123f-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e123f-183">Ref</span><span class="sxs-lookup"><span data-stu-id="e123f-183">Ref</span></span>|<span data-ttu-id="e123f-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="e123f-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="e123f-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="e123f-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="e123f-188">Throw</span><span class="sxs-lookup"><span data-stu-id="e123f-188">Throw</span></span>|<span data-ttu-id="e123f-189">Throw</span><span class="sxs-lookup"><span data-stu-id="e123f-189">Throw</span></span>|<span data-ttu-id="e123f-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="e123f-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="e123f-191">Association</span></span><br /><br /> <span data-ttu-id="e123f-192">Typ</span><span class="sxs-lookup"><span data-stu-id="e123f-192">type</span></span>|<span data-ttu-id="e123f-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-194">Throw</span><span class="sxs-lookup"><span data-stu-id="e123f-194">Throw</span></span>|<span data-ttu-id="e123f-195">Throw</span><span class="sxs-lookup"><span data-stu-id="e123f-195">Throw</span></span>|<span data-ttu-id="e123f-196">Throw</span><span class="sxs-lookup"><span data-stu-id="e123f-196">Throw</span></span>|<span data-ttu-id="e123f-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="e123f-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="e123f-200"><sup>1</sup> Die Verweise der angegebenen Entitätstyp Instanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e123f-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="e123f-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e123f-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="e123f-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="e123f-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="e123f-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="e123f-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="e123f-204"><sup>2</sup> Eigenschaften komplexer Typen werden vereinfacht, bevor Sie an den Speicher gesendet werden, sodass Sie vergleichbar sind (solange alle Eigenschaften vergleichbar sind).</span><span class="sxs-lookup"><span data-stu-id="e123f-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="e123f-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="e123f-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="e123f-206"><sup>3</sup> Die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine sinnvolle Ausnahme aus, ohne den Anbieter bzw. den Speicher einzubinden.</span><span class="sxs-lookup"><span data-stu-id="e123f-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="e123f-207"><sup>4</sup> Es wurde versucht, alle Eigenschaften zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="e123f-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="e123f-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e123f-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="e123f-209"><sup>5</sup> Alle einzelnen Elemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und alle Schlüsseleigenschaften des Entitäts Typs ein).</span><span class="sxs-lookup"><span data-stu-id="e123f-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e123f-210">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e123f-210">See also</span></span>

- [<span data-ttu-id="e123f-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e123f-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
