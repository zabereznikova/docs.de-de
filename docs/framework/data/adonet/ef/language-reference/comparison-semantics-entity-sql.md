---
title: Vergleichssemantik (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083334"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d344a-102">Vergleichssemantik (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d344a-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d344a-103">Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:</span><span class="sxs-lookup"><span data-stu-id="d344a-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d344a-104">Expliziter Vergleich</span><span class="sxs-lookup"><span data-stu-id="d344a-104">Explicit comparison</span></span>  
 <span data-ttu-id="d344a-105">Gleichheitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="d344a-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="d344a-106">!=</span><span class="sxs-lookup"><span data-stu-id="d344a-106">!=</span></span>  
  
 <span data-ttu-id="d344a-107">Sortieroperationen:</span><span class="sxs-lookup"><span data-stu-id="d344a-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="d344a-108">NULL-Zulässigkeitsoperationen:</span><span class="sxs-lookup"><span data-stu-id="d344a-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="d344a-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="d344a-109">IS NULL</span></span>  
  
-   <span data-ttu-id="d344a-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d344a-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d344a-111">Explizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="d344a-111">Explicit distinction</span></span>  
 <span data-ttu-id="d344a-112">Gleichheitsunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="d344a-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="d344a-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d344a-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="d344a-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d344a-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d344a-115">Sortierunterscheidung:</span><span class="sxs-lookup"><span data-stu-id="d344a-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="d344a-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d344a-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d344a-117">Implizite Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="d344a-117">Implicit distinction</span></span>  
 <span data-ttu-id="d344a-118">Mengenoperationen und Prädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="d344a-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="d344a-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d344a-119">UNION</span></span>  
  
-   <span data-ttu-id="d344a-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d344a-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="d344a-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d344a-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="d344a-122">SET</span><span class="sxs-lookup"><span data-stu-id="d344a-122">SET</span></span>  
  
-   <span data-ttu-id="d344a-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d344a-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d344a-124">Elementprädikate (Gleichheit):</span><span class="sxs-lookup"><span data-stu-id="d344a-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="d344a-125">IN</span><span class="sxs-lookup"><span data-stu-id="d344a-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d344a-126">Unterstützte Kombinationen</span><span class="sxs-lookup"><span data-stu-id="d344a-126">Supported Combinations</span></span>  
 <span data-ttu-id="d344a-127">In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d344a-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d344a-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="d344a-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d344a-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="d344a-129">**!=**</span></span>|<span data-ttu-id="d344a-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d344a-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d344a-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="d344a-131">**DISTINCT**</span></span>|<span data-ttu-id="d344a-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d344a-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d344a-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d344a-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d344a-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d344a-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d344a-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d344a-135">**SET**</span></span><br /><br /> <span data-ttu-id="d344a-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d344a-136">**OVERLAPS**</span></span>|<span data-ttu-id="d344a-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d344a-137">**IN**</span></span>|<span data-ttu-id="d344a-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d344a-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d344a-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d344a-139">**>   >=**</span></span>|<span data-ttu-id="d344a-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d344a-140">**ORDER BY**</span></span>|<span data-ttu-id="d344a-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="d344a-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d344a-142">**IST NICHT NULL**</span><span class="sxs-lookup"><span data-stu-id="d344a-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d344a-143">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="d344a-143">Entity type</span></span>|<span data-ttu-id="d344a-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d344a-145">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d344a-146">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d344a-147">Alle Eigenschaften<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d344a-148">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-149">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d344a-151">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="d344a-151">Complex type</span></span>|<span data-ttu-id="d344a-152">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-153">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-154">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-155">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-156">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-157">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-158">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d344a-159">Zeile</span><span class="sxs-lookup"><span data-stu-id="d344a-159">Row</span></span>|<span data-ttu-id="d344a-160">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d344a-161">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d344a-162">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d344a-163">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-164">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-165">Alle Eigenschaften<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d344a-166">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d344a-167">Primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="d344a-167">Primitive type</span></span>|<span data-ttu-id="d344a-168">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-168">Provider-specific</span></span>|<span data-ttu-id="d344a-169">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-169">Provider-specific</span></span>|<span data-ttu-id="d344a-170">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-170">Provider-specific</span></span>|<span data-ttu-id="d344a-171">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-171">Provider-specific</span></span>|<span data-ttu-id="d344a-172">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-172">Provider-specific</span></span>|<span data-ttu-id="d344a-173">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-173">Provider-specific</span></span>|<span data-ttu-id="d344a-174">Anbieterspezifisch</span><span class="sxs-lookup"><span data-stu-id="d344a-174">Provider-specific</span></span>|  
|<span data-ttu-id="d344a-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="d344a-175">Multiset</span></span>|<span data-ttu-id="d344a-176">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-177">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-178">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-179">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-180">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-181">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-182">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d344a-183">Ref</span><span class="sxs-lookup"><span data-stu-id="d344a-183">Ref</span></span>|<span data-ttu-id="d344a-184">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d344a-185">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d344a-186">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d344a-187">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d344a-188">Throw</span><span class="sxs-lookup"><span data-stu-id="d344a-188">Throw</span></span>|<span data-ttu-id="d344a-189">Throw</span><span class="sxs-lookup"><span data-stu-id="d344a-189">Throw</span></span>|<span data-ttu-id="d344a-190">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d344a-191">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="d344a-191">Association</span></span><br /><br /> <span data-ttu-id="d344a-192">Typ</span><span class="sxs-lookup"><span data-stu-id="d344a-192">type</span></span>|<span data-ttu-id="d344a-193">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-194">Throw</span><span class="sxs-lookup"><span data-stu-id="d344a-194">Throw</span></span>|<span data-ttu-id="d344a-195">Throw</span><span class="sxs-lookup"><span data-stu-id="d344a-195">Throw</span></span>|<span data-ttu-id="d344a-196">Throw</span><span class="sxs-lookup"><span data-stu-id="d344a-196">Throw</span></span>|<span data-ttu-id="d344a-197">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-198">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d344a-199">Löst<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d344a-200"><sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d344a-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d344a-201">Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="d344a-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d344a-202">Eine Ausnahme wird ausgelöst, wenn dies versucht wird.</span><span class="sxs-lookup"><span data-stu-id="d344a-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d344a-203">Folgende Abfrage löst beispielsweise eine Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="d344a-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d344a-204"><sup>2</sup>Eigenschaften komplexer Typen werden bevor Sie an den Speicher gesendet werden, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="d344a-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d344a-205">Siehe auch <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="d344a-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d344a-206"><sup>3</sup>Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne dass der Anbieter/Speicher.</span><span class="sxs-lookup"><span data-stu-id="d344a-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d344a-207"><sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d344a-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d344a-208">Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d344a-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d344a-209"><sup>5</sup>alle Einzelelemente der Verweise werden verglichen (Dies schließt den Namen der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).</span><span class="sxs-lookup"><span data-stu-id="d344a-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d344a-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d344a-210">See also</span></span>

- [<span data-ttu-id="d344a-211">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d344a-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
