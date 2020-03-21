---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150453"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="20c63-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="20c63-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="20c63-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="20c63-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="20c63-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="20c63-104">Explicit comparison</span></span>  
 <span data-ttu-id="20c63-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="20c63-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="20c63-106">!=</span><span class="sxs-lookup"><span data-stu-id="20c63-106">!=</span></span>  
  
 <span data-ttu-id="20c63-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="20c63-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="20c63-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="20c63-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="20c63-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="20c63-109">IS NULL</span></span>  
  
- <span data-ttu-id="20c63-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="20c63-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="20c63-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="20c63-111">Explicit distinction</span></span>  
 <span data-ttu-id="20c63-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="20c63-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="20c63-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="20c63-113">DISTINCT</span></span>  
  
- <span data-ttu-id="20c63-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="20c63-114">GROUP BY</span></span>  
  
 <span data-ttu-id="20c63-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="20c63-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="20c63-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="20c63-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="20c63-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="20c63-117">Implicit distinction</span></span>  
 <span data-ttu-id="20c63-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="20c63-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="20c63-119">UNION</span><span class="sxs-lookup"><span data-stu-id="20c63-119">UNION</span></span>  
  
- <span data-ttu-id="20c63-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="20c63-120">INTERSECT</span></span>  
  
- <span data-ttu-id="20c63-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="20c63-121">EXCEPT</span></span>  
  
- <span data-ttu-id="20c63-122">SET</span><span class="sxs-lookup"><span data-stu-id="20c63-122">SET</span></span>  
  
- <span data-ttu-id="20c63-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="20c63-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="20c63-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="20c63-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="20c63-125">IN</span><span class="sxs-lookup"><span data-stu-id="20c63-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="20c63-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="20c63-126">Supported Combinations</span></span>  
 <span data-ttu-id="20c63-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="20c63-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="20c63-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="20c63-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="20c63-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="20c63-129">**!=**</span></span>|<span data-ttu-id="20c63-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="20c63-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="20c63-131">**Unterschiedliche**</span><span class="sxs-lookup"><span data-stu-id="20c63-131">**DISTINCT**</span></span>|<span data-ttu-id="20c63-132">**Union**</span><span class="sxs-lookup"><span data-stu-id="20c63-132">**UNION**</span></span><br /><br /> <span data-ttu-id="20c63-133">**Schneiden**</span><span class="sxs-lookup"><span data-stu-id="20c63-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="20c63-134">**Außer**</span><span class="sxs-lookup"><span data-stu-id="20c63-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="20c63-135">**Festgelegt**</span><span class="sxs-lookup"><span data-stu-id="20c63-135">**SET**</span></span><br /><br /> <span data-ttu-id="20c63-136">**Überschneidungen**</span><span class="sxs-lookup"><span data-stu-id="20c63-136">**OVERLAPS**</span></span>|<span data-ttu-id="20c63-137">**In**</span><span class="sxs-lookup"><span data-stu-id="20c63-137">**IN**</span></span>|<span data-ttu-id="20c63-138">**< <=**</span><span class="sxs-lookup"><span data-stu-id="20c63-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="20c63-139">**> >=**</span><span class="sxs-lookup"><span data-stu-id="20c63-139">**>   >=**</span></span>|<span data-ttu-id="20c63-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="20c63-140">**ORDER BY**</span></span>|<span data-ttu-id="20c63-141">**IST NULL**</span><span class="sxs-lookup"><span data-stu-id="20c63-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="20c63-142">**IST NICHT NULL**</span><span class="sxs-lookup"><span data-stu-id="20c63-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="20c63-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="20c63-143">Entity type</span></span>|<span data-ttu-id="20c63-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="20c63-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="20c63-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="20c63-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="20c63-148">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-149">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="20c63-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="20c63-151">Complex type</span></span>|<span data-ttu-id="20c63-152">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-153">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-154">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-155">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-156">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-157">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-158">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="20c63-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="20c63-159">Row</span></span>|<span data-ttu-id="20c63-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="20c63-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="20c63-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="20c63-163">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-164">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="20c63-166">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="20c63-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="20c63-167">Primitive type</span></span>|<span data-ttu-id="20c63-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-168">Provider-specific</span></span>|<span data-ttu-id="20c63-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-169">Provider-specific</span></span>|<span data-ttu-id="20c63-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-170">Provider-specific</span></span>|<span data-ttu-id="20c63-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-171">Provider-specific</span></span>|<span data-ttu-id="20c63-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-172">Provider-specific</span></span>|<span data-ttu-id="20c63-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-173">Provider-specific</span></span>|<span data-ttu-id="20c63-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="20c63-174">Provider-specific</span></span>|  
|<span data-ttu-id="20c63-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="20c63-175">Multiset</span></span>|<span data-ttu-id="20c63-176">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-177">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-178">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-179">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-180">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-181">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-182">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="20c63-183">Ref</span><span class="sxs-lookup"><span data-stu-id="20c63-183">Ref</span></span>|<span data-ttu-id="20c63-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="20c63-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="20c63-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="20c63-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="20c63-188">Throw</span><span class="sxs-lookup"><span data-stu-id="20c63-188">Throw</span></span>|<span data-ttu-id="20c63-189">Throw</span><span class="sxs-lookup"><span data-stu-id="20c63-189">Throw</span></span>|<span data-ttu-id="20c63-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="20c63-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="20c63-191">Association</span></span><br /><br /> <span data-ttu-id="20c63-192">type</span><span class="sxs-lookup"><span data-stu-id="20c63-192">type</span></span>|<span data-ttu-id="20c63-193">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-194">Throw</span><span class="sxs-lookup"><span data-stu-id="20c63-194">Throw</span></span>|<span data-ttu-id="20c63-195">Throw</span><span class="sxs-lookup"><span data-stu-id="20c63-195">Throw</span></span>|<span data-ttu-id="20c63-196">Throw</span><span class="sxs-lookup"><span data-stu-id="20c63-196">Throw</span></span>|<span data-ttu-id="20c63-197">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-198">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="20c63-199">Wurf<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="20c63-200"><sup>1</sup> Die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="20c63-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="20c63-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="20c63-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="20c63-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="20c63-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="20c63-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="20c63-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="20c63-204"><sup>2</sup> Eigenschaften komplexer Typen werden abgeflacht, bevor sie an den Speicher gesendet werden, so dass sie vergleichbar werden (solange alle ihre Eigenschaften vergleichbar sind).</span><span class="sxs-lookup"><span data-stu-id="20c63-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="20c63-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="20c63-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="20c63-206"><sup>3</sup> Die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine sinnvolle Ausnahme aus, ohne den Anbieter/Speicher einzubinden.</span><span class="sxs-lookup"><span data-stu-id="20c63-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="20c63-207"><sup>4</sup> Es wird versucht, alle Eigenschaften zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="20c63-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="20c63-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="20c63-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="20c63-209"><sup>5</sup> Alle einzelnen Elemente der Referenzen werden verglichen (dies schließt den Entitätssatznamen und alle Schlüsseleigenschaften des Entitätstyps ein).</span><span class="sxs-lookup"><span data-stu-id="20c63-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c63-210">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20c63-210">See also</span></span>

- [<span data-ttu-id="20c63-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="20c63-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
