---
title: Entity SQL-Kurzreferenz
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 7ec3b6fc184b4f169d6f6489bda0ec8fa4abb4f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148139"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="62036-102">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="62036-102">Entity SQL Quick Reference</span></span>

<span data-ttu-id="62036-103">Dieses Thema enthält eine Kurzreferenz zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="62036-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="62036-104">Die Abfragen in diesem Thema basieren auf dem AdventureWorks Sales-Modell.</span><span class="sxs-lookup"><span data-stu-id="62036-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="62036-105">Literale</span><span class="sxs-lookup"><span data-stu-id="62036-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="62036-106">String</span><span class="sxs-lookup"><span data-stu-id="62036-106">String</span></span>  

 <span data-ttu-id="62036-107">Es gibt Zeichenfolgenliterale, die aus Unicode-, und solche, die aus Nicht-Unicode-Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="62036-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="62036-108">Unicode-Zeichen folgen wird N vorangesteht. Beispiel: `N'hello'` .</span><span class="sxs-lookup"><span data-stu-id="62036-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="62036-109">Im Folgenden ist ein Beispiel für ein nicht-Unicode-Zeichenfolgenliteral abgebildet:</span><span class="sxs-lookup"><span data-stu-id="62036-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="62036-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-110">Output:</span></span>  
  
|<span data-ttu-id="62036-111">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-112">Hello</span><span class="sxs-lookup"><span data-stu-id="62036-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="62036-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="62036-113">DateTime</span></span>  

 <span data-ttu-id="62036-114">In DateTime-Literalen sind sowohl das Datum als auch die Uhrzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="62036-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="62036-115">Es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="62036-115">There are no default values.</span></span>  
  
 <span data-ttu-id="62036-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="62036-117">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-117">Output:</span></span>  
  
|<span data-ttu-id="62036-118">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="62036-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="62036-120">Integer</span><span class="sxs-lookup"><span data-stu-id="62036-120">Integer</span></span>  

 <span data-ttu-id="62036-121">Ganzzahlige Literale können vom Typ Int32 (123), UInt32 (123U), Int64 (123L) und UInt64 (123UL) sein.</span><span class="sxs-lookup"><span data-stu-id="62036-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="62036-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="62036-123">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-123">Output:</span></span>  
  
|<span data-ttu-id="62036-124">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-125">1</span><span class="sxs-lookup"><span data-stu-id="62036-125">1</span></span>|  
|<span data-ttu-id="62036-126">2</span><span class="sxs-lookup"><span data-stu-id="62036-126">2</span></span>|  
|<span data-ttu-id="62036-127">3</span><span class="sxs-lookup"><span data-stu-id="62036-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="62036-128">Andere</span><span class="sxs-lookup"><span data-stu-id="62036-128">Other</span></span>  

 <span data-ttu-id="62036-129">Andere von  unterstützte Literale sind Guid, Binary, Float/Double, Decimal und .</span><span class="sxs-lookup"><span data-stu-id="62036-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="62036-130">NULL-Literale werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als mit allen anderen Typen im kozeptionellen Modell kompatibel aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="62036-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="62036-131">Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="62036-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="62036-132">ROW</span><span class="sxs-lookup"><span data-stu-id="62036-132">ROW</span></span>  

 <span data-ttu-id="62036-133">[Row](row-entity-sql.md) erstellt einen anonymen, strukturell typisierten (Datensatz-) Wert wie in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="62036-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="62036-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="62036-135">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-135">Output:</span></span>  
  
|<span data-ttu-id="62036-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="62036-136">ProductID</span></span>|<span data-ttu-id="62036-137">Name</span><span class="sxs-lookup"><span data-stu-id="62036-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="62036-138">1</span><span class="sxs-lookup"><span data-stu-id="62036-138">1</span></span>|<span data-ttu-id="62036-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="62036-139">Adjustable Race</span></span>|  
|<span data-ttu-id="62036-140">879</span><span class="sxs-lookup"><span data-stu-id="62036-140">879</span></span>|<span data-ttu-id="62036-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="62036-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="62036-142">712</span><span class="sxs-lookup"><span data-stu-id="62036-142">712</span></span>|<span data-ttu-id="62036-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="62036-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="62036-144">...</span><span class="sxs-lookup"><span data-stu-id="62036-144">...</span></span>|<span data-ttu-id="62036-145">...</span><span class="sxs-lookup"><span data-stu-id="62036-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="62036-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="62036-146">MULTISET</span></span>  

 <span data-ttu-id="62036-147">[Multiset](multiset-entity-sql.md) -Konstrukte, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="62036-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="62036-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="62036-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="62036-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="62036-150">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-150">Output:</span></span>  
  
|<span data-ttu-id="62036-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="62036-151">ProductID</span></span>|<span data-ttu-id="62036-152">Name</span><span class="sxs-lookup"><span data-stu-id="62036-152">Name</span></span>|<span data-ttu-id="62036-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="62036-153">ProductNumber</span></span>|<span data-ttu-id="62036-154">…</span><span class="sxs-lookup"><span data-stu-id="62036-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="62036-155">842</span><span class="sxs-lookup"><span data-stu-id="62036-155">842</span></span>|<span data-ttu-id="62036-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="62036-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="62036-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="62036-157">PA-T100</span></span>|<span data-ttu-id="62036-158">…</span><span class="sxs-lookup"><span data-stu-id="62036-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="62036-159">Object</span><span class="sxs-lookup"><span data-stu-id="62036-159">Object</span></span>  

 <span data-ttu-id="62036-160">[Konstruktorkonstrukte benannter Typen](named-type-constructor-entity-sql.md) (benannte) benutzerdefinierte Objekte, z `person("abc", 12)` . b..</span><span class="sxs-lookup"><span data-stu-id="62036-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="62036-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="62036-162">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-162">Output:</span></span>  
  
|<span data-ttu-id="62036-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="62036-163">SalesOrderDetailID</span></span>|<span data-ttu-id="62036-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="62036-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="62036-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="62036-165">OrderQty</span></span>|<span data-ttu-id="62036-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="62036-166">ProductID</span></span>|<span data-ttu-id="62036-167">...</span><span class="sxs-lookup"><span data-stu-id="62036-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="62036-168">1</span><span class="sxs-lookup"><span data-stu-id="62036-168">1</span></span>|<span data-ttu-id="62036-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="62036-169">4911-403C-98</span></span>|<span data-ttu-id="62036-170">1</span><span class="sxs-lookup"><span data-stu-id="62036-170">1</span></span>|<span data-ttu-id="62036-171">776</span><span class="sxs-lookup"><span data-stu-id="62036-171">776</span></span>|<span data-ttu-id="62036-172">...</span><span class="sxs-lookup"><span data-stu-id="62036-172">...</span></span>|  
|<span data-ttu-id="62036-173">2</span><span class="sxs-lookup"><span data-stu-id="62036-173">2</span></span>|<span data-ttu-id="62036-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="62036-174">4911-403C-98</span></span>|<span data-ttu-id="62036-175">3</span><span class="sxs-lookup"><span data-stu-id="62036-175">3</span></span>|<span data-ttu-id="62036-176">777</span><span class="sxs-lookup"><span data-stu-id="62036-176">777</span></span>|<span data-ttu-id="62036-177">...</span><span class="sxs-lookup"><span data-stu-id="62036-177">...</span></span>|  
|<span data-ttu-id="62036-178">...</span><span class="sxs-lookup"><span data-stu-id="62036-178">...</span></span>|<span data-ttu-id="62036-179">...</span><span class="sxs-lookup"><span data-stu-id="62036-179">...</span></span>|<span data-ttu-id="62036-180">...</span><span class="sxs-lookup"><span data-stu-id="62036-180">...</span></span>|<span data-ttu-id="62036-181">...</span><span class="sxs-lookup"><span data-stu-id="62036-181">...</span></span>|<span data-ttu-id="62036-182">...</span><span class="sxs-lookup"><span data-stu-id="62036-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="62036-183">References</span><span class="sxs-lookup"><span data-stu-id="62036-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="62036-184">REF</span><span class="sxs-lookup"><span data-stu-id="62036-184">REF</span></span>  

 <span data-ttu-id="62036-185">[Ref](ref-entity-sql.md) erstellt einen Verweis auf eine Entitätstyp Instanz.</span><span class="sxs-lookup"><span data-stu-id="62036-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="62036-186">Die folgende Abfrage gibt beispielsweise einen Verweis auf jede Order-Entität in der Orders-Entitätenmenge zurück:</span><span class="sxs-lookup"><span data-stu-id="62036-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="62036-187">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-187">Output:</span></span>  
  
|<span data-ttu-id="62036-188">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-189">1</span><span class="sxs-lookup"><span data-stu-id="62036-189">1</span></span>|  
|<span data-ttu-id="62036-190">2</span><span class="sxs-lookup"><span data-stu-id="62036-190">2</span></span>|  
|<span data-ttu-id="62036-191">3</span><span class="sxs-lookup"><span data-stu-id="62036-191">3</span></span>|  
|<span data-ttu-id="62036-192">...</span><span class="sxs-lookup"><span data-stu-id="62036-192">...</span></span>|  
  
 <span data-ttu-id="62036-193">Im folgenden Beispiel wird der Eigenschaftsextrahierungsoperator (.) für den Zugriff auf eine Eigenschaft einer Entität verwendet.</span><span class="sxs-lookup"><span data-stu-id="62036-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="62036-194">Bei der Verwendung des Eigenschaftsextraktionsoperators wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="62036-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="62036-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="62036-196">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-196">Output:</span></span>  
  
|<span data-ttu-id="62036-197">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="62036-198">Adjustable Race</span></span>|  
|<span data-ttu-id="62036-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="62036-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="62036-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="62036-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="62036-201">...</span><span class="sxs-lookup"><span data-stu-id="62036-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="62036-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="62036-202">DEREF</span></span>  

 <span data-ttu-id="62036-203">[Deref](deref-entity-sql.md) dereferenziert einen Verweis Wert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="62036-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="62036-204">Die folgende Abfrage erstellt beispielsweise die Order-Entitäten für jede Bestellung in der Orders-Entitätenmenge: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="62036-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="62036-205">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="62036-206">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-206">Output:</span></span>  
  
|<span data-ttu-id="62036-207">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="62036-208">Adjustable Race</span></span>|  
|<span data-ttu-id="62036-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="62036-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="62036-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="62036-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="62036-211">...</span><span class="sxs-lookup"><span data-stu-id="62036-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="62036-212">CREATEREF UND KEY</span><span class="sxs-lookup"><span data-stu-id="62036-212">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="62036-213">" [Kreateref](createref-entity-sql.md) " erstellt einen Verweis, der einen Schlüssel übergibt.</span><span class="sxs-lookup"><span data-stu-id="62036-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="62036-214">[Key](key-entity-sql.md) extrahiert den Schlüsselteil eines Ausdrucks mit Typverweis.</span><span class="sxs-lookup"><span data-stu-id="62036-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="62036-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="62036-216">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-216">Output:</span></span>  
  
|<span data-ttu-id="62036-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="62036-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="62036-218">980</span><span class="sxs-lookup"><span data-stu-id="62036-218">980</span></span>|  
|<span data-ttu-id="62036-219">365</span><span class="sxs-lookup"><span data-stu-id="62036-219">365</span></span>|  
|<span data-ttu-id="62036-220">771</span><span class="sxs-lookup"><span data-stu-id="62036-220">771</span></span>|  
|<span data-ttu-id="62036-221">...</span><span class="sxs-lookup"><span data-stu-id="62036-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="62036-222">Functions</span><span class="sxs-lookup"><span data-stu-id="62036-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="62036-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="62036-223">Canonical</span></span>  

 <span data-ttu-id="62036-224">Der Namespace für [kanonische Funktionen](canonical-functions.md) ist EDM, wie in `Edm.Length("string")` .</span><span class="sxs-lookup"><span data-stu-id="62036-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="62036-225">Der Namespace muss nur dann angegeben werden, wenn ein anderer Namespace importiert wurde, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="62036-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="62036-226">Wenn zwei Namespaces über die gleiche Funktion verfügen, sollte der Benutzer den vollständigen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="62036-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="62036-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="62036-228">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-228">Output:</span></span>  
  
|<span data-ttu-id="62036-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="62036-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="62036-230">6</span><span class="sxs-lookup"><span data-stu-id="62036-230">6</span></span>|  
|<span data-ttu-id="62036-231">6</span><span class="sxs-lookup"><span data-stu-id="62036-231">6</span></span>|  
|<span data-ttu-id="62036-232">5</span><span class="sxs-lookup"><span data-stu-id="62036-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="62036-233">Microsoft-anbieterspezifische Funktionen</span><span class="sxs-lookup"><span data-stu-id="62036-233">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="62036-234">[Microsoft-anbieterspezifische Funktionen](../sqlclient-for-ef-functions.md) befinden sich im- `SqlServer` Namespace.</span><span class="sxs-lookup"><span data-stu-id="62036-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="62036-235">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="62036-236">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-236">Output:</span></span>  
  
|<span data-ttu-id="62036-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="62036-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="62036-238">27</span><span class="sxs-lookup"><span data-stu-id="62036-238">27</span></span>|  
|<span data-ttu-id="62036-239">27</span><span class="sxs-lookup"><span data-stu-id="62036-239">27</span></span>|  
|<span data-ttu-id="62036-240">26</span><span class="sxs-lookup"><span data-stu-id="62036-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="62036-241">Namespaces</span><span class="sxs-lookup"><span data-stu-id="62036-241">Namespaces</span></span>  

 <span data-ttu-id="62036-242">Die [Verwendung](using-entity-sql.md) von gibt in einem Abfrage Ausdruck verwendete Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="62036-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="62036-243">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="62036-244">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-244">Output:</span></span>  
  
|<span data-ttu-id="62036-245">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-246">aa</span><span class="sxs-lookup"><span data-stu-id="62036-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="62036-247">Paging</span><span class="sxs-lookup"><span data-stu-id="62036-247">Paging</span></span>  

 <span data-ttu-id="62036-248">Paging kann ausgedrückt werden, indem Sie eine [Skip](skip-entity-sql.md) -und [Limit](limit-entity-sql.md) -Unterklausel in der [Order by](order-by-entity-sql.md) -Klausel deklarieren.</span><span class="sxs-lookup"><span data-stu-id="62036-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="62036-249">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="62036-250">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-250">Output:</span></span>  
  
|<span data-ttu-id="62036-251">id</span><span class="sxs-lookup"><span data-stu-id="62036-251">ID</span></span>|<span data-ttu-id="62036-252">Name</span><span class="sxs-lookup"><span data-stu-id="62036-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="62036-253">10</span><span class="sxs-lookup"><span data-stu-id="62036-253">10</span></span>|<span data-ttu-id="62036-254">Adina</span><span class="sxs-lookup"><span data-stu-id="62036-254">Adina</span></span>|  
|<span data-ttu-id="62036-255">11</span><span class="sxs-lookup"><span data-stu-id="62036-255">11</span></span>|<span data-ttu-id="62036-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="62036-256">Agcaoili</span></span>|  
|<span data-ttu-id="62036-257">12</span><span class="sxs-lookup"><span data-stu-id="62036-257">12</span></span>|<span data-ttu-id="62036-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="62036-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="62036-259">Gruppierung</span><span class="sxs-lookup"><span data-stu-id="62036-259">Grouping</span></span>  

 <span data-ttu-id="62036-260">[Gruppieren nach](group-by-entity-sql.md) gibt Gruppen an, in die von einem Abfrage Ausdruck ([Select](select-entity-sql.md)) zurückgegebene Objekte eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="62036-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="62036-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="62036-262">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-262">Output:</span></span>  
  
|<span data-ttu-id="62036-263">name</span><span class="sxs-lookup"><span data-stu-id="62036-263">name</span></span>|  
|----------|  
|<span data-ttu-id="62036-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="62036-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="62036-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="62036-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="62036-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="62036-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="62036-267">...</span><span class="sxs-lookup"><span data-stu-id="62036-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="62036-268">Navigation</span><span class="sxs-lookup"><span data-stu-id="62036-268">Navigation</span></span>  

 <span data-ttu-id="62036-269">Der Beziehungsnavigationsoperator ermöglicht die Navigation der Beziehung von einer Entität (an einem Ende) zu einer anderen Entität (am anderen Ende).</span><span class="sxs-lookup"><span data-stu-id="62036-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="62036-270">[Navigate](navigate-entity-sql.md) übernimmt den Beziehungstyp als \<namespace> . \<relationship type name></span><span class="sxs-lookup"><span data-stu-id="62036-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="62036-271">Navigate gibt Ref zurück \<T> , wenn die Kardinalität des "to"-Endes "1" ist.</span><span class="sxs-lookup"><span data-stu-id="62036-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="62036-272">Wenn die Kardinalität des "to"-Endes "n" ist, wird die Auflistung<Ref \<T>> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62036-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="62036-273">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="62036-274">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-274">Output:</span></span>  
  
|<span data-ttu-id="62036-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="62036-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="62036-276">1</span><span class="sxs-lookup"><span data-stu-id="62036-276">1</span></span>|  
|<span data-ttu-id="62036-277">2</span><span class="sxs-lookup"><span data-stu-id="62036-277">2</span></span>|  
|<span data-ttu-id="62036-278">3</span><span class="sxs-lookup"><span data-stu-id="62036-278">3</span></span>|  
|<span data-ttu-id="62036-279">...</span><span class="sxs-lookup"><span data-stu-id="62036-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="62036-280">SELECT VALUE UND SELECT</span><span class="sxs-lookup"><span data-stu-id="62036-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="62036-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="62036-281">SELECT VALUE</span></span>  

 <span data-ttu-id="62036-282"> stellt die SELECT VALUE-Klausel bereit, um die implizite Zeilenkonstruktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="62036-282">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="62036-283">In einer SELECT VALUE-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="62036-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="62036-284">Wenn eine solche Klausel verwendet wird, wird kein Zeilen Wrapper um die Elemente in der SELECT-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden, z. b `SELECT VALUE a` .:.</span><span class="sxs-lookup"><span data-stu-id="62036-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="62036-285">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="62036-286">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-286">Output:</span></span>  
  
|<span data-ttu-id="62036-287">Name</span><span class="sxs-lookup"><span data-stu-id="62036-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="62036-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="62036-288">Adjustable Race</span></span>|  
|<span data-ttu-id="62036-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="62036-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="62036-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="62036-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="62036-291">...</span><span class="sxs-lookup"><span data-stu-id="62036-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="62036-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="62036-292">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="62036-293">stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="62036-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="62036-294">SELECT werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit Feldern, z. B.: .</span><span class="sxs-lookup"><span data-stu-id="62036-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="62036-295">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-295">Example:</span></span>  
  
 <span data-ttu-id="62036-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="62036-297">Name</span><span class="sxs-lookup"><span data-stu-id="62036-297">Name</span></span>|<span data-ttu-id="62036-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="62036-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="62036-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="62036-299">Adjustable Race</span></span>|<span data-ttu-id="62036-300">1</span><span class="sxs-lookup"><span data-stu-id="62036-300">1</span></span>|  
|<span data-ttu-id="62036-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="62036-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="62036-302">879</span><span class="sxs-lookup"><span data-stu-id="62036-302">879</span></span>|  
|<span data-ttu-id="62036-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="62036-303">AWC Logo Cap</span></span>|<span data-ttu-id="62036-304">712</span><span class="sxs-lookup"><span data-stu-id="62036-304">712</span></span>|  
|<span data-ttu-id="62036-305">...</span><span class="sxs-lookup"><span data-stu-id="62036-305">...</span></span>|<span data-ttu-id="62036-306">...</span><span class="sxs-lookup"><span data-stu-id="62036-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="62036-307">CASE EXPRESSION</span><span class="sxs-lookup"><span data-stu-id="62036-307">CASE EXPRESSION</span></span>  

 <span data-ttu-id="62036-308">Der [Case-Ausdruck](case-entity-sql.md) wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="62036-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="62036-309">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="62036-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="62036-310">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="62036-310">Output:</span></span>  
  
|<span data-ttu-id="62036-311">Wert</span><span class="sxs-lookup"><span data-stu-id="62036-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="62036-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="62036-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62036-313">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62036-313">See also</span></span>

- [<span data-ttu-id="62036-314">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="62036-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="62036-315">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62036-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
