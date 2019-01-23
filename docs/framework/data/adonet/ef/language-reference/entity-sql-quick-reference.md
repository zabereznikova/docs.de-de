---
title: Entity SQL-Kurzreferenz
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 20d8d1cb1e4b5cbf37dffcce6a7e79c2a4c265d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539402"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="6740d-102">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="6740d-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="6740d-103">Dieses Thema enthält eine Kurzreferenz zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="6740d-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="6740d-104">Die Abfragen in diesem Thema basieren auf dem AdventureWorks Sales-Modell.</span><span class="sxs-lookup"><span data-stu-id="6740d-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="6740d-105">Literale</span><span class="sxs-lookup"><span data-stu-id="6740d-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="6740d-106">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6740d-106">String</span></span>  
 <span data-ttu-id="6740d-107">Es gibt Zeichenfolgenliterale, die aus Unicode-, und solche, die aus Nicht-Unicode-Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="6740d-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="6740d-108">Unicode-Zeichenfolgen werden in n vorangestellt werden. Z. B. `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="6740d-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="6740d-109">Im Folgenden ist ein Beispiel für ein nicht-Unicode-Zeichenfolgenliteral abgebildet:</span><span class="sxs-lookup"><span data-stu-id="6740d-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="6740d-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-110">Output:</span></span>  
  
|<span data-ttu-id="6740d-111">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-112">hello</span><span class="sxs-lookup"><span data-stu-id="6740d-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="6740d-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="6740d-113">DateTime</span></span>  
 <span data-ttu-id="6740d-114">In DateTime-Literalen sind sowohl das Datum als auch die Uhrzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6740d-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="6740d-115">Es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="6740d-115">There are no default values.</span></span>  
  
 <span data-ttu-id="6740d-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="6740d-117">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-117">Output:</span></span>  
  
|<span data-ttu-id="6740d-118">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="6740d-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="6740d-120">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="6740d-120">Integer</span></span>  
 <span data-ttu-id="6740d-121">Ganzzahlige Literale können vom Typ Int32 (123), UInt32 (123U), Int64 (123L) und UInt64 (123UL) sein.</span><span class="sxs-lookup"><span data-stu-id="6740d-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="6740d-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="6740d-123">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-123">Output:</span></span>  
  
|<span data-ttu-id="6740d-124">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-125">1</span><span class="sxs-lookup"><span data-stu-id="6740d-125">1</span></span>|  
|<span data-ttu-id="6740d-126">2</span><span class="sxs-lookup"><span data-stu-id="6740d-126">2</span></span>|  
|<span data-ttu-id="6740d-127">3</span><span class="sxs-lookup"><span data-stu-id="6740d-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="6740d-128">Andere</span><span class="sxs-lookup"><span data-stu-id="6740d-128">Other</span></span>  
 <span data-ttu-id="6740d-129">Andere von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützte Literale sind Guid`null`, Binary, Float/Double, Decimal und .</span><span class="sxs-lookup"><span data-stu-id="6740d-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="6740d-130">NULL-Literale werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als mit allen anderen Typen im kozeptionellen Modell kompatibel aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="6740d-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="6740d-131">Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="6740d-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="6740d-132">ROW</span><span class="sxs-lookup"><span data-stu-id="6740d-132">ROW</span></span>  
 <span data-ttu-id="6740d-133">[Zeile](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) erstellt einen anonymen, strukturell typisierten (Datensatz-) Wert wie in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="6740d-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="6740d-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="6740d-135">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-135">Output:</span></span>  
  
|<span data-ttu-id="6740d-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="6740d-136">ProductID</span></span>|<span data-ttu-id="6740d-137">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="6740d-138">1</span><span class="sxs-lookup"><span data-stu-id="6740d-138">1</span></span>|<span data-ttu-id="6740d-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6740d-139">Adjustable Race</span></span>|  
|<span data-ttu-id="6740d-140">879</span><span class="sxs-lookup"><span data-stu-id="6740d-140">879</span></span>|<span data-ttu-id="6740d-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6740d-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6740d-142">712</span><span class="sxs-lookup"><span data-stu-id="6740d-142">712</span></span>|<span data-ttu-id="6740d-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6740d-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6740d-144">...</span><span class="sxs-lookup"><span data-stu-id="6740d-144">...</span></span>|<span data-ttu-id="6740d-145">...</span><span class="sxs-lookup"><span data-stu-id="6740d-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="6740d-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="6740d-146">MULTISET</span></span>  
 <span data-ttu-id="6740d-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) erstellt Auflistungen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="6740d-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="6740d-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="6740d-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="6740d-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="6740d-150">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-150">Output:</span></span>  
  
|<span data-ttu-id="6740d-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="6740d-151">ProductID</span></span>|<span data-ttu-id="6740d-152">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-152">Name</span></span>|<span data-ttu-id="6740d-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="6740d-153">ProductNumber</span></span>|<span data-ttu-id="6740d-154">…</span><span class="sxs-lookup"><span data-stu-id="6740d-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="6740d-155">842</span><span class="sxs-lookup"><span data-stu-id="6740d-155">842</span></span>|<span data-ttu-id="6740d-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="6740d-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="6740d-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="6740d-157">PA-T100</span></span>|<span data-ttu-id="6740d-158">…</span><span class="sxs-lookup"><span data-stu-id="6740d-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="6740d-159">Object</span><span class="sxs-lookup"><span data-stu-id="6740d-159">Object</span></span>  
 <span data-ttu-id="6740d-160">[Mit dem Namen Typkonstruktor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) erstellt (benannte) benutzerdefinierte Objekte, z. B. `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="6740d-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="6740d-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="6740d-162">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-162">Output:</span></span>  
  
|<span data-ttu-id="6740d-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="6740d-163">SalesOrderDetailID</span></span>|<span data-ttu-id="6740d-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="6740d-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="6740d-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="6740d-165">OrderQty</span></span>|<span data-ttu-id="6740d-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="6740d-166">ProductID</span></span>|<span data-ttu-id="6740d-167">...</span><span class="sxs-lookup"><span data-stu-id="6740d-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="6740d-168">1</span><span class="sxs-lookup"><span data-stu-id="6740d-168">1</span></span>|<span data-ttu-id="6740d-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6740d-169">4911-403C-98</span></span>|<span data-ttu-id="6740d-170">1</span><span class="sxs-lookup"><span data-stu-id="6740d-170">1</span></span>|<span data-ttu-id="6740d-171">776</span><span class="sxs-lookup"><span data-stu-id="6740d-171">776</span></span>|<span data-ttu-id="6740d-172">...</span><span class="sxs-lookup"><span data-stu-id="6740d-172">...</span></span>|  
|<span data-ttu-id="6740d-173">2</span><span class="sxs-lookup"><span data-stu-id="6740d-173">2</span></span>|<span data-ttu-id="6740d-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6740d-174">4911-403C-98</span></span>|<span data-ttu-id="6740d-175">3</span><span class="sxs-lookup"><span data-stu-id="6740d-175">3</span></span>|<span data-ttu-id="6740d-176">777</span><span class="sxs-lookup"><span data-stu-id="6740d-176">777</span></span>|<span data-ttu-id="6740d-177">...</span><span class="sxs-lookup"><span data-stu-id="6740d-177">...</span></span>|  
|<span data-ttu-id="6740d-178">...</span><span class="sxs-lookup"><span data-stu-id="6740d-178">...</span></span>|<span data-ttu-id="6740d-179">...</span><span class="sxs-lookup"><span data-stu-id="6740d-179">...</span></span>|<span data-ttu-id="6740d-180">...</span><span class="sxs-lookup"><span data-stu-id="6740d-180">...</span></span>|<span data-ttu-id="6740d-181">...</span><span class="sxs-lookup"><span data-stu-id="6740d-181">...</span></span>|<span data-ttu-id="6740d-182">...</span><span class="sxs-lookup"><span data-stu-id="6740d-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="6740d-183">Verweise</span><span class="sxs-lookup"><span data-stu-id="6740d-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6740d-184">REF</span><span class="sxs-lookup"><span data-stu-id="6740d-184">REF</span></span>  
 <span data-ttu-id="6740d-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) erstellt einen Verweis auf eine Instanz eines Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="6740d-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="6740d-186">Die folgende Abfrage gibt beispielsweise einen Verweis auf jede Order-Entität in der Orders-Entitätenmenge zurück:</span><span class="sxs-lookup"><span data-stu-id="6740d-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="6740d-187">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-187">Output:</span></span>  
  
|<span data-ttu-id="6740d-188">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-189">1</span><span class="sxs-lookup"><span data-stu-id="6740d-189">1</span></span>|  
|<span data-ttu-id="6740d-190">2</span><span class="sxs-lookup"><span data-stu-id="6740d-190">2</span></span>|  
|<span data-ttu-id="6740d-191">3</span><span class="sxs-lookup"><span data-stu-id="6740d-191">3</span></span>|  
|<span data-ttu-id="6740d-192">...</span><span class="sxs-lookup"><span data-stu-id="6740d-192">...</span></span>|  
  
 <span data-ttu-id="6740d-193">Im folgenden Beispiel wird der Eigenschaftsextrahierungsoperator (.) für den Zugriff auf eine Eigenschaft einer Entität verwendet.</span><span class="sxs-lookup"><span data-stu-id="6740d-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="6740d-194">Bei der Verwendung des Eigenschaftsextraktionsoperators wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="6740d-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="6740d-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6740d-196">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-196">Output:</span></span>  
  
|<span data-ttu-id="6740d-197">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6740d-198">Adjustable Race</span></span>|  
|<span data-ttu-id="6740d-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6740d-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6740d-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6740d-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6740d-201">...</span><span class="sxs-lookup"><span data-stu-id="6740d-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="6740d-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="6740d-202">DEREF</span></span>  
 <span data-ttu-id="6740d-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="6740d-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="6740d-204">Die folgende Abfrage erstellt beispielsweise die Order-Entitäten für jede Bestellung in der Orders-Entitätenmenge: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="6740d-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="6740d-205">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6740d-206">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-206">Output:</span></span>  
  
|<span data-ttu-id="6740d-207">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6740d-208">Adjustable Race</span></span>|  
|<span data-ttu-id="6740d-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6740d-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6740d-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6740d-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6740d-211">...</span><span class="sxs-lookup"><span data-stu-id="6740d-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="6740d-212">CREATEREF UND KEY</span><span class="sxs-lookup"><span data-stu-id="6740d-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="6740d-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) erstellt einen Verweis, der einen Schlüssel übergibt.</span><span class="sxs-lookup"><span data-stu-id="6740d-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="6740d-214">[Schlüssel](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrahiert den Schlüsselteil eines Ausdrucks mit Typverweis.</span><span class="sxs-lookup"><span data-stu-id="6740d-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="6740d-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6740d-216">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-216">Output:</span></span>  
  
|<span data-ttu-id="6740d-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="6740d-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="6740d-218">980</span><span class="sxs-lookup"><span data-stu-id="6740d-218">980</span></span>|  
|<span data-ttu-id="6740d-219">365</span><span class="sxs-lookup"><span data-stu-id="6740d-219">365</span></span>|  
|<span data-ttu-id="6740d-220">771</span><span class="sxs-lookup"><span data-stu-id="6740d-220">771</span></span>|  
|<span data-ttu-id="6740d-221">...</span><span class="sxs-lookup"><span data-stu-id="6740d-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="6740d-222">Funktionen</span><span class="sxs-lookup"><span data-stu-id="6740d-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="6740d-223">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6740d-223">Canonical</span></span>  
 <span data-ttu-id="6740d-224">Der Namespace für [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) ist Edm, wie in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="6740d-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="6740d-225">Der Namespace muss nur dann angegeben werden, wenn ein anderer Namespace importiert wurde, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="6740d-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="6740d-226">Wenn zwei Namespaces über die gleiche Funktion verfügen, sollte der Benutzer den vollständigen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="6740d-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="6740d-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6740d-228">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-228">Output:</span></span>  
  
|<span data-ttu-id="6740d-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="6740d-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="6740d-230">6</span><span class="sxs-lookup"><span data-stu-id="6740d-230">6</span></span>|  
|<span data-ttu-id="6740d-231">6</span><span class="sxs-lookup"><span data-stu-id="6740d-231">6</span></span>|  
|<span data-ttu-id="6740d-232">5</span><span class="sxs-lookup"><span data-stu-id="6740d-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="6740d-233">Microsoft-anbieterspezifische Funktionen</span><span class="sxs-lookup"><span data-stu-id="6740d-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="6740d-234">[Microsoft-anbieterspezifische Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) befinden sich in der `SqlServer` Namespace.</span><span class="sxs-lookup"><span data-stu-id="6740d-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="6740d-235">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6740d-236">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-236">Output:</span></span>  
  
|<span data-ttu-id="6740d-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="6740d-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="6740d-238">27</span><span class="sxs-lookup"><span data-stu-id="6740d-238">27</span></span>|  
|<span data-ttu-id="6740d-239">27</span><span class="sxs-lookup"><span data-stu-id="6740d-239">27</span></span>|  
|<span data-ttu-id="6740d-240">26</span><span class="sxs-lookup"><span data-stu-id="6740d-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="6740d-241">Namespaces</span><span class="sxs-lookup"><span data-stu-id="6740d-241">Namespaces</span></span>  
 <span data-ttu-id="6740d-242">[Mithilfe von](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) gibt an, in einem Abfrageausdruck verwendete Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6740d-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="6740d-243">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="6740d-244">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-244">Output:</span></span>  
  
|<span data-ttu-id="6740d-245">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-246">aa</span><span class="sxs-lookup"><span data-stu-id="6740d-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="6740d-247">Paging</span><span class="sxs-lookup"><span data-stu-id="6740d-247">Paging</span></span>  
 <span data-ttu-id="6740d-248">Paging ausgedrückt werden kann, indem Sie deklarieren eine [überspringen](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) und [Grenzwert](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="6740d-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="6740d-249">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="6740d-250">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-250">Output:</span></span>  
  
|<span data-ttu-id="6740d-251">ID</span><span class="sxs-lookup"><span data-stu-id="6740d-251">ID</span></span>|<span data-ttu-id="6740d-252">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="6740d-253">10</span><span class="sxs-lookup"><span data-stu-id="6740d-253">10</span></span>|<span data-ttu-id="6740d-254">Adina</span><span class="sxs-lookup"><span data-stu-id="6740d-254">Adina</span></span>|  
|<span data-ttu-id="6740d-255">11</span><span class="sxs-lookup"><span data-stu-id="6740d-255">11</span></span>|<span data-ttu-id="6740d-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="6740d-256">Agcaoili</span></span>|  
|<span data-ttu-id="6740d-257">12</span><span class="sxs-lookup"><span data-stu-id="6740d-257">12</span></span>|<span data-ttu-id="6740d-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="6740d-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="6740d-259">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="6740d-259">Grouping</span></span>  
 <span data-ttu-id="6740d-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) gibt Gruppen an, in die von einer Abfrage zurückgegebenen Objekte ([wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6740d-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="6740d-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="6740d-262">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-262">Output:</span></span>  
  
|<span data-ttu-id="6740d-263">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-263">name</span></span>|  
|----------|  
|<span data-ttu-id="6740d-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6740d-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6740d-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6740d-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6740d-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6740d-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6740d-267">...</span><span class="sxs-lookup"><span data-stu-id="6740d-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="6740d-268">Navigation</span><span class="sxs-lookup"><span data-stu-id="6740d-268">Navigation</span></span>  
 <span data-ttu-id="6740d-269">Der Beziehungsnavigationsoperator ermöglicht die Navigation der Beziehung von einer Entität (an einem Ende) zu einer anderen Entität (am anderen Ende).</span><span class="sxs-lookup"><span data-stu-id="6740d-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="6740d-270">[Navigieren Sie](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) wird der Beziehungstyp als qualifiziert \<Namespace >.\< Beziehungstypname >.</span><span class="sxs-lookup"><span data-stu-id="6740d-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="6740d-271">Navigieren Sie gibt Ref\<T > Wenn die Kardinalität der das Beenden ist 1.</span><span class="sxs-lookup"><span data-stu-id="6740d-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="6740d-272">Wenn die Kardinalität der das Beenden ist n, die Auflistung < Ref\<T >> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6740d-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="6740d-273">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="6740d-274">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-274">Output:</span></span>  
  
|<span data-ttu-id="6740d-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="6740d-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="6740d-276">1</span><span class="sxs-lookup"><span data-stu-id="6740d-276">1</span></span>|  
|<span data-ttu-id="6740d-277">2</span><span class="sxs-lookup"><span data-stu-id="6740d-277">2</span></span>|  
|<span data-ttu-id="6740d-278">3</span><span class="sxs-lookup"><span data-stu-id="6740d-278">3</span></span>|  
|<span data-ttu-id="6740d-279">...</span><span class="sxs-lookup"><span data-stu-id="6740d-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="6740d-280">SELECT VALUE UND SELECT</span><span class="sxs-lookup"><span data-stu-id="6740d-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="6740d-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="6740d-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6740d-282">stellt die SELECT VALUE-Klausel bereit, um die implizite Zeilenkonstruktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="6740d-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="6740d-283">In einer SELECT VALUE-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6740d-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="6740d-284">Wenn diese Klausel verwendet wird, kein Zeilen-Wrapper für die Elemente in der SELECT-Klausel erstellt wird und eine Auflistung der gewünschten Form werden, z. B. erstellt kann: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="6740d-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="6740d-285">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6740d-286">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-286">Output:</span></span>  
  
|<span data-ttu-id="6740d-287">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="6740d-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6740d-288">Adjustable Race</span></span>|  
|<span data-ttu-id="6740d-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6740d-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6740d-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6740d-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6740d-291">...</span><span class="sxs-lookup"><span data-stu-id="6740d-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="6740d-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="6740d-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6740d-293">stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="6740d-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="6740d-294">SELECT`SELECT a, b, c` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit Feldern, z. B.: .</span><span class="sxs-lookup"><span data-stu-id="6740d-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="6740d-295">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-295">Example:</span></span>  
  
 <span data-ttu-id="6740d-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="6740d-297">Name</span><span class="sxs-lookup"><span data-stu-id="6740d-297">Name</span></span>|<span data-ttu-id="6740d-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="6740d-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="6740d-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6740d-299">Adjustable Race</span></span>|<span data-ttu-id="6740d-300">1</span><span class="sxs-lookup"><span data-stu-id="6740d-300">1</span></span>|  
|<span data-ttu-id="6740d-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6740d-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="6740d-302">879</span><span class="sxs-lookup"><span data-stu-id="6740d-302">879</span></span>|  
|<span data-ttu-id="6740d-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6740d-303">AWC Logo Cap</span></span>|<span data-ttu-id="6740d-304">712</span><span class="sxs-lookup"><span data-stu-id="6740d-304">712</span></span>|  
|<span data-ttu-id="6740d-305">...</span><span class="sxs-lookup"><span data-stu-id="6740d-305">...</span></span>|<span data-ttu-id="6740d-306">...</span><span class="sxs-lookup"><span data-stu-id="6740d-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="6740d-307">CASE EXPRESSION</span><span class="sxs-lookup"><span data-stu-id="6740d-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="6740d-308">Die [case-Ausdruck](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6740d-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="6740d-309">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6740d-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="6740d-310">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6740d-310">Output:</span></span>  
  
|<span data-ttu-id="6740d-311">Wert</span><span class="sxs-lookup"><span data-stu-id="6740d-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6740d-312">true</span><span class="sxs-lookup"><span data-stu-id="6740d-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6740d-313">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6740d-313">See also</span></span>
- [<span data-ttu-id="6740d-314">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6740d-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6740d-315">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6740d-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
