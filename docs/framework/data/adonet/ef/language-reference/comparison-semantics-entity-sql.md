---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605970"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="12e2c-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="12e2c-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="12e2c-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="12e2c-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="12e2c-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="12e2c-104">Explicit comparison</span></span>  
 <span data-ttu-id="12e2c-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="12e2c-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="12e2c-106">!=</span><span class="sxs-lookup"><span data-stu-id="12e2c-106">!=</span></span>  
  
 <span data-ttu-id="12e2c-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="12e2c-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="12e2c-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="12e2c-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="12e2c-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="12e2c-109">IS NULL</span></span>  
  
- <span data-ttu-id="12e2c-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="12e2c-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="12e2c-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="12e2c-111">Explicit distinction</span></span>  
 <span data-ttu-id="12e2c-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="12e2c-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="12e2c-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="12e2c-113">DISTINCT</span></span>  
  
- <span data-ttu-id="12e2c-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="12e2c-114">GROUP BY</span></span>  
  
 <span data-ttu-id="12e2c-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="12e2c-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="12e2c-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="12e2c-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="12e2c-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="12e2c-117">Implicit distinction</span></span>  
 <span data-ttu-id="12e2c-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="12e2c-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="12e2c-119">UNION</span><span class="sxs-lookup"><span data-stu-id="12e2c-119">UNION</span></span>  
  
- <span data-ttu-id="12e2c-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="12e2c-120">INTERSECT</span></span>  
  
- <span data-ttu-id="12e2c-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="12e2c-121">EXCEPT</span></span>  
  
- <span data-ttu-id="12e2c-122">SET</span><span class="sxs-lookup"><span data-stu-id="12e2c-122">SET</span></span>  
  
- <span data-ttu-id="12e2c-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="12e2c-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="12e2c-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="12e2c-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="12e2c-125">IN</span><span class="sxs-lookup"><span data-stu-id="12e2c-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="12e2c-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="12e2c-126">Supported Combinations</span></span>  
 <span data-ttu-id="12e2c-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="12e2c-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="12e2c-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="12e2c-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="12e2c-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="12e2c-129">**!=**</span></span>|<span data-ttu-id="12e2c-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="12e2c-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="12e2c-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="12e2c-131">**DISTINCT**</span></span>|<span data-ttu-id="12e2c-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="12e2c-132">**UNION**</span></span><br /><br /> <span data-ttu-id="12e2c-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="12e2c-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="12e2c-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="12e2c-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="12e2c-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="12e2c-135">**SET**</span></span><br /><br /> <span data-ttu-id="12e2c-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="12e2c-136">**OVERLAPS**</span></span>|<span data-ttu-id="12e2c-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="12e2c-137">**IN**</span></span>|<span data-ttu-id="12e2c-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="12e2c-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="12e2c-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="12e2c-139">**>   >=**</span></span>|<span data-ttu-id="12e2c-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="12e2c-140">**ORDER BY**</span></span>|<span data-ttu-id="12e2c-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="12e2c-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="12e2c-142">**IST NICHT NULL**</span><span class="sxs-lookup"><span data-stu-id="12e2c-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="12e2c-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="12e2c-143">Entity type</span></span>|<span data-ttu-id="12e2c-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="12e2c-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="12e2c-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="12e2c-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="12e2c-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="12e2c-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="12e2c-151">Complex type</span></span>|<span data-ttu-id="12e2c-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="12e2c-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="12e2c-159">Row</span></span>|<span data-ttu-id="12e2c-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="12e2c-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="12e2c-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="12e2c-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="12e2c-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="12e2c-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="12e2c-167">Primitive type</span></span>|<span data-ttu-id="12e2c-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-168">Provider-specific</span></span>|<span data-ttu-id="12e2c-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-169">Provider-specific</span></span>|<span data-ttu-id="12e2c-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-170">Provider-specific</span></span>|<span data-ttu-id="12e2c-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-171">Provider-specific</span></span>|<span data-ttu-id="12e2c-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-172">Provider-specific</span></span>|<span data-ttu-id="12e2c-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-173">Provider-specific</span></span>|<span data-ttu-id="12e2c-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="12e2c-174">Provider-specific</span></span>|  
|<span data-ttu-id="12e2c-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="12e2c-175">Multiset</span></span>|<span data-ttu-id="12e2c-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="12e2c-183">Ref</span><span class="sxs-lookup"><span data-stu-id="12e2c-183">Ref</span></span>|<span data-ttu-id="12e2c-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="12e2c-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="12e2c-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="12e2c-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="12e2c-188">Throw</span><span class="sxs-lookup"><span data-stu-id="12e2c-188">Throw</span></span>|<span data-ttu-id="12e2c-189">Throw</span><span class="sxs-lookup"><span data-stu-id="12e2c-189">Throw</span></span>|<span data-ttu-id="12e2c-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="12e2c-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="12e2c-191">Association</span></span><br /><br /> <span data-ttu-id="12e2c-192">Typ</span><span class="sxs-lookup"><span data-stu-id="12e2c-192">type</span></span>|<span data-ttu-id="12e2c-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-194">Throw</span><span class="sxs-lookup"><span data-stu-id="12e2c-194">Throw</span></span>|<span data-ttu-id="12e2c-195">Throw</span><span class="sxs-lookup"><span data-stu-id="12e2c-195">Throw</span></span>|<span data-ttu-id="12e2c-196">Throw</span><span class="sxs-lookup"><span data-stu-id="12e2c-196">Throw</span></span>|<span data-ttu-id="12e2c-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="12e2c-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="12e2c-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="12e2c-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="12e2c-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="12e2c-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="12e2c-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="12e2c-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="12e2c-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="12e2c-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="12e2c-204"><sup>2</sup>Eigenschaften komplexer Typen werden bevor Sie an den Speicher gesendet werden, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="12e2c-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="12e2c-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="12e2c-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="12e2c-206"><sup>3</sup>Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne dass der Anbieter/Speicher.</span><span class="sxs-lookup"><span data-stu-id="12e2c-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="12e2c-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="12e2c-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="12e2c-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="12e2c-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="12e2c-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="12e2c-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e2c-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12e2c-210">See also</span></span>

- [<span data-ttu-id="12e2c-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="12e2c-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
