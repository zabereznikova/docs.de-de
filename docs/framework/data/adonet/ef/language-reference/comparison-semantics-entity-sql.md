---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2ca91861d4830321168e96fb200c4889dc33b04b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631715"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="006c6-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="006c6-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="006c6-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="006c6-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="006c6-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="006c6-104">Explicit comparison</span></span>  
 <span data-ttu-id="006c6-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="006c6-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="006c6-106">!=</span><span class="sxs-lookup"><span data-stu-id="006c6-106">!=</span></span>  
  
 <span data-ttu-id="006c6-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="006c6-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="006c6-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="006c6-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="006c6-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="006c6-109">IS NULL</span></span>  
  
- <span data-ttu-id="006c6-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="006c6-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="006c6-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="006c6-111">Explicit distinction</span></span>  
 <span data-ttu-id="006c6-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="006c6-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="006c6-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="006c6-113">DISTINCT</span></span>  
  
- <span data-ttu-id="006c6-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="006c6-114">GROUP BY</span></span>  
  
 <span data-ttu-id="006c6-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="006c6-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="006c6-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="006c6-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="006c6-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="006c6-117">Implicit distinction</span></span>  
 <span data-ttu-id="006c6-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="006c6-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="006c6-119">UNION</span><span class="sxs-lookup"><span data-stu-id="006c6-119">UNION</span></span>  
  
- <span data-ttu-id="006c6-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="006c6-120">INTERSECT</span></span>  
  
- <span data-ttu-id="006c6-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="006c6-121">EXCEPT</span></span>  
  
- <span data-ttu-id="006c6-122">SET</span><span class="sxs-lookup"><span data-stu-id="006c6-122">SET</span></span>  
  
- <span data-ttu-id="006c6-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="006c6-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="006c6-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="006c6-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="006c6-125">IN</span><span class="sxs-lookup"><span data-stu-id="006c6-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="006c6-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="006c6-126">Supported Combinations</span></span>  
 <span data-ttu-id="006c6-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="006c6-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="006c6-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="006c6-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="006c6-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="006c6-129">**!=**</span></span>|<span data-ttu-id="006c6-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="006c6-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="006c6-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="006c6-131">**DISTINCT**</span></span>|<span data-ttu-id="006c6-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="006c6-132">**UNION**</span></span><br /><br /> <span data-ttu-id="006c6-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="006c6-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="006c6-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="006c6-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="006c6-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="006c6-135">**SET**</span></span><br /><br /> <span data-ttu-id="006c6-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="006c6-136">**OVERLAPS**</span></span>|<span data-ttu-id="006c6-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="006c6-137">**IN**</span></span>|<span data-ttu-id="006c6-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="006c6-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="006c6-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="006c6-139">**>   >=**</span></span>|<span data-ttu-id="006c6-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="006c6-140">**ORDER BY**</span></span>|<span data-ttu-id="006c6-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="006c6-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="006c6-142">**IST NICHT NULL**</span><span class="sxs-lookup"><span data-stu-id="006c6-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="006c6-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="006c6-143">Entity type</span></span>|<span data-ttu-id="006c6-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="006c6-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="006c6-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="006c6-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="006c6-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="006c6-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="006c6-151">Complex type</span></span>|<span data-ttu-id="006c6-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="006c6-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="006c6-159">Row</span></span>|<span data-ttu-id="006c6-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="006c6-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="006c6-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="006c6-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="006c6-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="006c6-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="006c6-167">Primitive type</span></span>|<span data-ttu-id="006c6-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-168">Provider-specific</span></span>|<span data-ttu-id="006c6-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-169">Provider-specific</span></span>|<span data-ttu-id="006c6-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-170">Provider-specific</span></span>|<span data-ttu-id="006c6-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-171">Provider-specific</span></span>|<span data-ttu-id="006c6-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-172">Provider-specific</span></span>|<span data-ttu-id="006c6-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-173">Provider-specific</span></span>|<span data-ttu-id="006c6-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="006c6-174">Provider-specific</span></span>|  
|<span data-ttu-id="006c6-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="006c6-175">Multiset</span></span>|<span data-ttu-id="006c6-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="006c6-183">Ref</span><span class="sxs-lookup"><span data-stu-id="006c6-183">Ref</span></span>|<span data-ttu-id="006c6-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="006c6-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="006c6-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="006c6-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="006c6-188">Throw</span><span class="sxs-lookup"><span data-stu-id="006c6-188">Throw</span></span>|<span data-ttu-id="006c6-189">Throw</span><span class="sxs-lookup"><span data-stu-id="006c6-189">Throw</span></span>|<span data-ttu-id="006c6-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="006c6-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="006c6-191">Association</span></span><br /><br /> <span data-ttu-id="006c6-192">Typ</span><span class="sxs-lookup"><span data-stu-id="006c6-192">type</span></span>|<span data-ttu-id="006c6-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-194">Throw</span><span class="sxs-lookup"><span data-stu-id="006c6-194">Throw</span></span>|<span data-ttu-id="006c6-195">Throw</span><span class="sxs-lookup"><span data-stu-id="006c6-195">Throw</span></span>|<span data-ttu-id="006c6-196">Throw</span><span class="sxs-lookup"><span data-stu-id="006c6-196">Throw</span></span>|<span data-ttu-id="006c6-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="006c6-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="006c6-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="006c6-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="006c6-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="006c6-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="006c6-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="006c6-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="006c6-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="006c6-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="006c6-204"><sup>2</sup>Eigenschaften komplexer Typen werden bevor Sie an den Speicher gesendet werden, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="006c6-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="006c6-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="006c6-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="006c6-206"><sup>3</sup>Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne dass der Anbieter/Speicher.</span><span class="sxs-lookup"><span data-stu-id="006c6-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="006c6-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="006c6-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="006c6-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="006c6-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="006c6-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="006c6-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006c6-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="006c6-210">See also</span></span>

- [<span data-ttu-id="006c6-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="006c6-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
