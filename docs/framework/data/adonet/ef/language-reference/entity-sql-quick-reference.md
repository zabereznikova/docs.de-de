---
title: Entity SQL-Kurzreferenz
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207070"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="a6974-102">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="a6974-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="a6974-103">Dieses Thema enthält eine Kurzreferenz zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="a6974-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="a6974-104">Die Abfragen in diesem Thema basieren auf dem AdventureWorks Sales-Modell.</span><span class="sxs-lookup"><span data-stu-id="a6974-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="a6974-105">Literale</span><span class="sxs-lookup"><span data-stu-id="a6974-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="a6974-106">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a6974-106">String</span></span>  
 <span data-ttu-id="a6974-107">Es gibt Zeichenfolgenliterale, die aus Unicode-, und solche, die aus Nicht-Unicode-Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="a6974-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="a6974-108">Unicode-Zeichenfolgen werden in n vorangestellt werden. Z. B. `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="a6974-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="a6974-109">Im Folgenden ist ein Beispiel für ein nicht-Unicode-Zeichenfolgenliteral abgebildet:</span><span class="sxs-lookup"><span data-stu-id="a6974-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="a6974-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-110">Output:</span></span>  
  
|<span data-ttu-id="a6974-111">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-112">hello</span><span class="sxs-lookup"><span data-stu-id="a6974-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="a6974-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="a6974-113">DateTime</span></span>  
 <span data-ttu-id="a6974-114">In DateTime-Literalen sind sowohl das Datum als auch die Uhrzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a6974-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="a6974-115">Es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="a6974-115">There are no default values.</span></span>  
  
 <span data-ttu-id="a6974-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="a6974-117">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-117">Output:</span></span>  
  
|<span data-ttu-id="a6974-118">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="a6974-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="a6974-120">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="a6974-120">Integer</span></span>  
 <span data-ttu-id="a6974-121">Ganzzahlige Literale können vom Typ Int32 (123), UInt32 (123U), Int64 (123L) und UInt64 (123UL) sein.</span><span class="sxs-lookup"><span data-stu-id="a6974-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="a6974-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="a6974-123">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-123">Output:</span></span>  
  
|<span data-ttu-id="a6974-124">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-125">1</span><span class="sxs-lookup"><span data-stu-id="a6974-125">1</span></span>|  
|<span data-ttu-id="a6974-126">2</span><span class="sxs-lookup"><span data-stu-id="a6974-126">2</span></span>|  
|<span data-ttu-id="a6974-127">3</span><span class="sxs-lookup"><span data-stu-id="a6974-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="a6974-128">Andere</span><span class="sxs-lookup"><span data-stu-id="a6974-128">Other</span></span>  
 <span data-ttu-id="a6974-129">Andere von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützte Literale sind Guid`null`, Binary, Float/Double, Decimal und .</span><span class="sxs-lookup"><span data-stu-id="a6974-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="a6974-130">NULL-Literale werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als mit allen anderen Typen im kozeptionellen Modell kompatibel aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="a6974-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="a6974-131">Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="a6974-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="a6974-132">ROW</span><span class="sxs-lookup"><span data-stu-id="a6974-132">ROW</span></span>  
 <span data-ttu-id="a6974-133">[Zeile](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) erstellt einen anonymen, strukturell typisierten (Datensatz-) Wert wie in:</span><span class="sxs-lookup"><span data-stu-id="a6974-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="a6974-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="a6974-135">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-135">Output:</span></span>  
  
|<span data-ttu-id="a6974-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="a6974-136">ProductID</span></span>|<span data-ttu-id="a6974-137">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="a6974-138">1</span><span class="sxs-lookup"><span data-stu-id="a6974-138">1</span></span>|<span data-ttu-id="a6974-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a6974-139">Adjustable Race</span></span>|  
|<span data-ttu-id="a6974-140">879</span><span class="sxs-lookup"><span data-stu-id="a6974-140">879</span></span>|<span data-ttu-id="a6974-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a6974-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a6974-142">712</span><span class="sxs-lookup"><span data-stu-id="a6974-142">712</span></span>|<span data-ttu-id="a6974-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a6974-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a6974-144">...</span><span class="sxs-lookup"><span data-stu-id="a6974-144">...</span></span>|<span data-ttu-id="a6974-145">...</span><span class="sxs-lookup"><span data-stu-id="a6974-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="a6974-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="a6974-146">MULTISET</span></span>  
 <span data-ttu-id="a6974-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) erstellt Auflistungen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="a6974-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="a6974-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="a6974-149">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-149">Output:</span></span>  
  
|<span data-ttu-id="a6974-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="a6974-150">ProductID</span></span>|<span data-ttu-id="a6974-151">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-151">Name</span></span>|<span data-ttu-id="a6974-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="a6974-152">ProductNumber</span></span>|<span data-ttu-id="a6974-153">…</span><span class="sxs-lookup"><span data-stu-id="a6974-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="a6974-154">842</span><span class="sxs-lookup"><span data-stu-id="a6974-154">842</span></span>|<span data-ttu-id="a6974-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="a6974-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="a6974-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="a6974-156">PA-T100</span></span>|<span data-ttu-id="a6974-157">…</span><span class="sxs-lookup"><span data-stu-id="a6974-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="a6974-158">Object</span><span class="sxs-lookup"><span data-stu-id="a6974-158">Object</span></span>  
 <span data-ttu-id="a6974-159">[Mit dem Namen Typkonstruktor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) erstellt (benannte) benutzerdefinierte Objekte, z. B. `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="a6974-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="a6974-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="a6974-161">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-161">Output:</span></span>  
  
|<span data-ttu-id="a6974-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="a6974-162">SalesOrderDetailID</span></span>|<span data-ttu-id="a6974-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="a6974-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="a6974-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="a6974-164">OrderQty</span></span>|<span data-ttu-id="a6974-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="a6974-165">ProductID</span></span>|<span data-ttu-id="a6974-166">...</span><span class="sxs-lookup"><span data-stu-id="a6974-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="a6974-167">1</span><span class="sxs-lookup"><span data-stu-id="a6974-167">1</span></span>|<span data-ttu-id="a6974-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a6974-168">4911-403C-98</span></span>|<span data-ttu-id="a6974-169">1</span><span class="sxs-lookup"><span data-stu-id="a6974-169">1</span></span>|<span data-ttu-id="a6974-170">776</span><span class="sxs-lookup"><span data-stu-id="a6974-170">776</span></span>|<span data-ttu-id="a6974-171">...</span><span class="sxs-lookup"><span data-stu-id="a6974-171">...</span></span>|  
|<span data-ttu-id="a6974-172">2</span><span class="sxs-lookup"><span data-stu-id="a6974-172">2</span></span>|<span data-ttu-id="a6974-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a6974-173">4911-403C-98</span></span>|<span data-ttu-id="a6974-174">3</span><span class="sxs-lookup"><span data-stu-id="a6974-174">3</span></span>|<span data-ttu-id="a6974-175">777</span><span class="sxs-lookup"><span data-stu-id="a6974-175">777</span></span>|<span data-ttu-id="a6974-176">...</span><span class="sxs-lookup"><span data-stu-id="a6974-176">...</span></span>|  
|<span data-ttu-id="a6974-177">...</span><span class="sxs-lookup"><span data-stu-id="a6974-177">...</span></span>|<span data-ttu-id="a6974-178">...</span><span class="sxs-lookup"><span data-stu-id="a6974-178">...</span></span>|<span data-ttu-id="a6974-179">...</span><span class="sxs-lookup"><span data-stu-id="a6974-179">...</span></span>|<span data-ttu-id="a6974-180">...</span><span class="sxs-lookup"><span data-stu-id="a6974-180">...</span></span>|<span data-ttu-id="a6974-181">...</span><span class="sxs-lookup"><span data-stu-id="a6974-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="a6974-182">Verweise</span><span class="sxs-lookup"><span data-stu-id="a6974-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a6974-183">REF</span><span class="sxs-lookup"><span data-stu-id="a6974-183">REF</span></span>  
 <span data-ttu-id="a6974-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) erstellt einen Verweis auf eine Instanz eines Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="a6974-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="a6974-185">Die folgende Abfrage gibt beispielsweise einen Verweis auf jede Order-Entität in der Orders-Entitätenmenge zurück:</span><span class="sxs-lookup"><span data-stu-id="a6974-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="a6974-186">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-186">Output:</span></span>  
  
|<span data-ttu-id="a6974-187">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-188">1</span><span class="sxs-lookup"><span data-stu-id="a6974-188">1</span></span>|  
|<span data-ttu-id="a6974-189">2</span><span class="sxs-lookup"><span data-stu-id="a6974-189">2</span></span>|  
|<span data-ttu-id="a6974-190">3</span><span class="sxs-lookup"><span data-stu-id="a6974-190">3</span></span>|  
|<span data-ttu-id="a6974-191">...</span><span class="sxs-lookup"><span data-stu-id="a6974-191">...</span></span>|  
  
 <span data-ttu-id="a6974-192">Im folgenden Beispiel wird der Eigenschaftsextrahierungsoperator (.) für den Zugriff auf eine Eigenschaft einer Entität verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6974-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="a6974-193">Bei der Verwendung des Eigenschaftsextraktionsoperators wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="a6974-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="a6974-194">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a6974-195">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-195">Output:</span></span>  
  
|<span data-ttu-id="a6974-196">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a6974-197">Adjustable Race</span></span>|  
|<span data-ttu-id="a6974-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a6974-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a6974-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a6974-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a6974-200">...</span><span class="sxs-lookup"><span data-stu-id="a6974-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="a6974-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="a6974-201">DEREF</span></span>  
 <span data-ttu-id="a6974-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="a6974-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="a6974-203">Die folgende Abfrage erstellt beispielsweise die Order-Entitäten für jede Bestellung in der Orders-Entitätenmenge: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="a6974-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="a6974-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a6974-205">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-205">Output:</span></span>  
  
|<span data-ttu-id="a6974-206">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a6974-207">Adjustable Race</span></span>|  
|<span data-ttu-id="a6974-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a6974-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a6974-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a6974-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a6974-210">...</span><span class="sxs-lookup"><span data-stu-id="a6974-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="a6974-211">CREATEREF UND KEY</span><span class="sxs-lookup"><span data-stu-id="a6974-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="a6974-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) erstellt einen Verweis, der einen Schlüssel übergibt.</span><span class="sxs-lookup"><span data-stu-id="a6974-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="a6974-213">[Schlüssel](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrahiert den Schlüsselteil eines Ausdrucks mit Typverweis.</span><span class="sxs-lookup"><span data-stu-id="a6974-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="a6974-214">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a6974-215">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-215">Output:</span></span>  
  
|<span data-ttu-id="a6974-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="a6974-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="a6974-217">980</span><span class="sxs-lookup"><span data-stu-id="a6974-217">980</span></span>|  
|<span data-ttu-id="a6974-218">365</span><span class="sxs-lookup"><span data-stu-id="a6974-218">365</span></span>|  
|<span data-ttu-id="a6974-219">771</span><span class="sxs-lookup"><span data-stu-id="a6974-219">771</span></span>|  
|<span data-ttu-id="a6974-220">...</span><span class="sxs-lookup"><span data-stu-id="a6974-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="a6974-221">Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6974-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="a6974-222">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6974-222">Canonical</span></span>  
 <span data-ttu-id="a6974-223">Der Namespace für [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) ist Edm, wie in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="a6974-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="a6974-224">Der Namespace muss nur dann angegeben werden, wenn ein anderer Namespace importiert wurde, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a6974-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="a6974-225">Wenn zwei Namespaces über die gleiche Funktion verfügen, sollte der Benutzer den vollständigen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="a6974-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="a6974-226">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a6974-227">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-227">Output:</span></span>  
  
|<span data-ttu-id="a6974-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="a6974-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="a6974-229">6</span><span class="sxs-lookup"><span data-stu-id="a6974-229">6</span></span>|  
|<span data-ttu-id="a6974-230">6</span><span class="sxs-lookup"><span data-stu-id="a6974-230">6</span></span>|  
|<span data-ttu-id="a6974-231">5</span><span class="sxs-lookup"><span data-stu-id="a6974-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="a6974-232">Microsoft-anbieterspezifische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6974-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="a6974-233">[Microsoft-anbieterspezifische Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) befinden sich in der `SqlServer` Namespace.</span><span class="sxs-lookup"><span data-stu-id="a6974-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="a6974-234">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a6974-235">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-235">Output:</span></span>  
  
|<span data-ttu-id="a6974-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="a6974-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="a6974-237">27</span><span class="sxs-lookup"><span data-stu-id="a6974-237">27</span></span>|  
|<span data-ttu-id="a6974-238">27</span><span class="sxs-lookup"><span data-stu-id="a6974-238">27</span></span>|  
|<span data-ttu-id="a6974-239">26</span><span class="sxs-lookup"><span data-stu-id="a6974-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="a6974-240">Namespaces</span><span class="sxs-lookup"><span data-stu-id="a6974-240">Namespaces</span></span>  
 <span data-ttu-id="a6974-241">[Mithilfe von](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) gibt an, in einem Abfrageausdruck verwendete Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a6974-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="a6974-242">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="a6974-243">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-243">Output:</span></span>  
  
|<span data-ttu-id="a6974-244">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-245">aa</span><span class="sxs-lookup"><span data-stu-id="a6974-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="a6974-246">Paging</span><span class="sxs-lookup"><span data-stu-id="a6974-246">Paging</span></span>  
 <span data-ttu-id="a6974-247">Paging ausgedrückt werden kann, indem Sie deklarieren eine [überspringen](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) und [Grenzwert](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) -Unterklausel in der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="a6974-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="a6974-248">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="a6974-249">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-249">Output:</span></span>  
  
|<span data-ttu-id="a6974-250">ID</span><span class="sxs-lookup"><span data-stu-id="a6974-250">ID</span></span>|<span data-ttu-id="a6974-251">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="a6974-252">10</span><span class="sxs-lookup"><span data-stu-id="a6974-252">10</span></span>|<span data-ttu-id="a6974-253">Adina</span><span class="sxs-lookup"><span data-stu-id="a6974-253">Adina</span></span>|  
|<span data-ttu-id="a6974-254">11</span><span class="sxs-lookup"><span data-stu-id="a6974-254">11</span></span>|<span data-ttu-id="a6974-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="a6974-255">Agcaoili</span></span>|  
|<span data-ttu-id="a6974-256">12</span><span class="sxs-lookup"><span data-stu-id="a6974-256">12</span></span>|<span data-ttu-id="a6974-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="a6974-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="a6974-258">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="a6974-258">Grouping</span></span>  
 <span data-ttu-id="a6974-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) gibt Gruppen an, in die von einer Abfrage zurückgegebenen Objekte ([wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a6974-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="a6974-260">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="a6974-261">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-261">Output:</span></span>  
  
|<span data-ttu-id="a6974-262">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-262">name</span></span>|  
|----------|  
|<span data-ttu-id="a6974-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a6974-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a6974-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a6974-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a6974-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a6974-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a6974-266">...</span><span class="sxs-lookup"><span data-stu-id="a6974-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="a6974-267">Navigation</span><span class="sxs-lookup"><span data-stu-id="a6974-267">Navigation</span></span>  
 <span data-ttu-id="a6974-268">Der Beziehungsnavigationsoperator ermöglicht die Navigation der Beziehung von einer Entität (an einem Ende) zu einer anderen Entität (am anderen Ende).</span><span class="sxs-lookup"><span data-stu-id="a6974-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="a6974-269">[Navigieren Sie](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) wird der Beziehungstyp als qualifiziert \<Namespace >.\< Beziehungstypname >.</span><span class="sxs-lookup"><span data-stu-id="a6974-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="a6974-270">Navigieren Sie gibt Ref\<T > Wenn die Kardinalität der das Beenden ist 1.</span><span class="sxs-lookup"><span data-stu-id="a6974-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="a6974-271">Wenn die Kardinalität der das Beenden ist n, die Auflistung < Ref\<T >> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6974-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="a6974-272">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="a6974-273">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-273">Output:</span></span>  
  
|<span data-ttu-id="a6974-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="a6974-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="a6974-275">1</span><span class="sxs-lookup"><span data-stu-id="a6974-275">1</span></span>|  
|<span data-ttu-id="a6974-276">2</span><span class="sxs-lookup"><span data-stu-id="a6974-276">2</span></span>|  
|<span data-ttu-id="a6974-277">3</span><span class="sxs-lookup"><span data-stu-id="a6974-277">3</span></span>|  
|<span data-ttu-id="a6974-278">...</span><span class="sxs-lookup"><span data-stu-id="a6974-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="a6974-279">SELECT VALUE UND SELECT</span><span class="sxs-lookup"><span data-stu-id="a6974-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="a6974-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="a6974-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a6974-281">Stellt den SELECT VALUE-Klausel, um die implizite Zeilenkonstruktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="a6974-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="a6974-282">In einer SELECT VALUE-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6974-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="a6974-283">Wenn diese Klausel verwendet wird, kein Zeilen-Wrapper für die Elemente in der SELECT-Klausel erstellt wird und eine Auflistung der gewünschten Form werden, z. B. erstellt kann: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="a6974-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="a6974-284">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="a6974-285">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-285">Output:</span></span>  
  
|<span data-ttu-id="a6974-286">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="a6974-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a6974-287">Adjustable Race</span></span>|  
|<span data-ttu-id="a6974-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a6974-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a6974-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a6974-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a6974-290">...</span><span class="sxs-lookup"><span data-stu-id="a6974-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="a6974-291">SELECT</span><span class="sxs-lookup"><span data-stu-id="a6974-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a6974-292">stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="a6974-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="a6974-293">SELECT`SELECT a, b, c` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit Feldern, z. B.: .</span><span class="sxs-lookup"><span data-stu-id="a6974-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="a6974-294">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-294">Example:</span></span>  
  
 <span data-ttu-id="a6974-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="a6974-296">Name</span><span class="sxs-lookup"><span data-stu-id="a6974-296">Name</span></span>|<span data-ttu-id="a6974-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="a6974-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="a6974-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a6974-298">Adjustable Race</span></span>|<span data-ttu-id="a6974-299">1</span><span class="sxs-lookup"><span data-stu-id="a6974-299">1</span></span>|  
|<span data-ttu-id="a6974-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a6974-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="a6974-301">879</span><span class="sxs-lookup"><span data-stu-id="a6974-301">879</span></span>|  
|<span data-ttu-id="a6974-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a6974-302">AWC Logo Cap</span></span>|<span data-ttu-id="a6974-303">712</span><span class="sxs-lookup"><span data-stu-id="a6974-303">712</span></span>|  
|<span data-ttu-id="a6974-304">...</span><span class="sxs-lookup"><span data-stu-id="a6974-304">...</span></span>|<span data-ttu-id="a6974-305">...</span><span class="sxs-lookup"><span data-stu-id="a6974-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="a6974-306">CASE EXPRESSION</span><span class="sxs-lookup"><span data-stu-id="a6974-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="a6974-307">Die [case-Ausdruck](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a6974-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="a6974-308">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6974-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="a6974-309">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a6974-309">Output:</span></span>  
  
|<span data-ttu-id="a6974-310">Wert</span><span class="sxs-lookup"><span data-stu-id="a6974-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a6974-311">true</span><span class="sxs-lookup"><span data-stu-id="a6974-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6974-312">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6974-312">See also</span></span>

- [<span data-ttu-id="a6974-313">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="a6974-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="a6974-314">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a6974-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
