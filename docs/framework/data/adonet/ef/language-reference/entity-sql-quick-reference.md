---
title: Entity SQL-Kurzreferenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 14d666624ac4572956364b3db3fd5ee7aad8799b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="8a0c9-102">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="8a0c9-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="8a0c9-103">Dieses Thema enthält eine Kurzreferenz zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="8a0c9-104">Die Abfragen in diesem Thema basieren auf dem AdventureWorks Sales-Modell.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="8a0c9-105">Literale</span><span class="sxs-lookup"><span data-stu-id="8a0c9-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="8a0c9-106">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8a0c9-106">String</span></span>  
 <span data-ttu-id="8a0c9-107">Es gibt Zeichenfolgenliterale, die aus Unicode-, und solche, die aus Nicht-Unicode-Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="8a0c9-108">Unicode-Zeichenfolgen sind "n" vorangestellt. Beispielsweise `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="8a0c9-109">Im Folgenden ist ein Beispiel für ein nicht-Unicode-Zeichenfolgenliteral abgebildet:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="8a0c9-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-110">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-111">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-112">hello</span><span class="sxs-lookup"><span data-stu-id="8a0c9-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="8a0c9-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="8a0c9-113">DateTime</span></span>  
 <span data-ttu-id="8a0c9-114">In DateTime-Literalen sind sowohl das Datum als auch die Uhrzeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="8a0c9-115">Es gibt keine Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-115">There are no default values.</span></span>  
  
 <span data-ttu-id="8a0c9-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="8a0c9-117">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-117">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-118">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="8a0c9-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="8a0c9-120">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="8a0c9-120">Integer</span></span>  
 <span data-ttu-id="8a0c9-121">Ganzzahlige Literale können vom Typ Int32 (123), UInt32 (123U), Int64 (123L) und UInt64 (123UL) sein.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="8a0c9-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="8a0c9-123">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-123">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-124">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-125">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-125">1</span></span>|  
|<span data-ttu-id="8a0c9-126">2</span><span class="sxs-lookup"><span data-stu-id="8a0c9-126">2</span></span>|  
|<span data-ttu-id="8a0c9-127">3</span><span class="sxs-lookup"><span data-stu-id="8a0c9-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="8a0c9-128">Andere</span><span class="sxs-lookup"><span data-stu-id="8a0c9-128">Other</span></span>  
 <span data-ttu-id="8a0c9-129">Andere von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützte Literale sind Guid`null`, Binary, Float/Double, Decimal und .</span><span class="sxs-lookup"><span data-stu-id="8a0c9-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="8a0c9-130">NULL-Literale werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als mit allen anderen Typen im kozeptionellen Modell kompatibel aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="8a0c9-131">Typkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="8a0c9-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="8a0c9-132">ROW</span><span class="sxs-lookup"><span data-stu-id="8a0c9-132">ROW</span></span>  
 <span data-ttu-id="8a0c9-133">[Zeile](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) einen anonymen, strukturell typisierte (Datensatz) Wert als in erstellt:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="8a0c9-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="8a0c9-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="8a0c9-135">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-135">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-136">ProductID</span></span>|<span data-ttu-id="8a0c9-137">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="8a0c9-138">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-138">1</span></span>|<span data-ttu-id="8a0c9-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8a0c9-139">Adjustable Race</span></span>|  
|<span data-ttu-id="8a0c9-140">879</span><span class="sxs-lookup"><span data-stu-id="8a0c9-140">879</span></span>|<span data-ttu-id="8a0c9-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8a0c9-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8a0c9-142">712</span><span class="sxs-lookup"><span data-stu-id="8a0c9-142">712</span></span>|<span data-ttu-id="8a0c9-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8a0c9-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8a0c9-144">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-144">...</span></span>|<span data-ttu-id="8a0c9-145">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="8a0c9-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="8a0c9-146">MULTISET</span></span>  
 <span data-ttu-id="8a0c9-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) Auflistungen, wie z. B. erstellt:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="8a0c9-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="8a0c9-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="8a0c9-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="8a0c9-150">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-150">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-151">ProductID</span></span>|<span data-ttu-id="8a0c9-152">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-152">Name</span></span>|<span data-ttu-id="8a0c9-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="8a0c9-153">ProductNumber</span></span>|<span data-ttu-id="8a0c9-154">…</span><span class="sxs-lookup"><span data-stu-id="8a0c9-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="8a0c9-155">842</span><span class="sxs-lookup"><span data-stu-id="8a0c9-155">842</span></span>|<span data-ttu-id="8a0c9-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="8a0c9-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="8a0c9-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="8a0c9-157">PA-T100</span></span>|<span data-ttu-id="8a0c9-158">…</span><span class="sxs-lookup"><span data-stu-id="8a0c9-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="8a0c9-159">Object</span><span class="sxs-lookup"><span data-stu-id="8a0c9-159">Object</span></span>  
 <span data-ttu-id="8a0c9-160">[Mit dem Namen Typkonstruktor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) erstellt (benannte) benutzerdefinierte Objekte, z. B. `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="8a0c9-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="8a0c9-162">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-162">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-163">SalesOrderDetailID</span></span>|<span data-ttu-id="8a0c9-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="8a0c9-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="8a0c9-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="8a0c9-165">OrderQty</span></span>|<span data-ttu-id="8a0c9-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-166">ProductID</span></span>|<span data-ttu-id="8a0c9-167">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="8a0c9-168">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-168">1</span></span>|<span data-ttu-id="8a0c9-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="8a0c9-169">4911-403C-98</span></span>|<span data-ttu-id="8a0c9-170">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-170">1</span></span>|<span data-ttu-id="8a0c9-171">776</span><span class="sxs-lookup"><span data-stu-id="8a0c9-171">776</span></span>|<span data-ttu-id="8a0c9-172">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-172">...</span></span>|  
|<span data-ttu-id="8a0c9-173">2</span><span class="sxs-lookup"><span data-stu-id="8a0c9-173">2</span></span>|<span data-ttu-id="8a0c9-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="8a0c9-174">4911-403C-98</span></span>|<span data-ttu-id="8a0c9-175">3</span><span class="sxs-lookup"><span data-stu-id="8a0c9-175">3</span></span>|<span data-ttu-id="8a0c9-176">777</span><span class="sxs-lookup"><span data-stu-id="8a0c9-176">777</span></span>|<span data-ttu-id="8a0c9-177">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-177">...</span></span>|  
|<span data-ttu-id="8a0c9-178">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-178">...</span></span>|<span data-ttu-id="8a0c9-179">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-179">...</span></span>|<span data-ttu-id="8a0c9-180">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-180">...</span></span>|<span data-ttu-id="8a0c9-181">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-181">...</span></span>|<span data-ttu-id="8a0c9-182">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="8a0c9-183">Verweise</span><span class="sxs-lookup"><span data-stu-id="8a0c9-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8a0c9-184">REF</span><span class="sxs-lookup"><span data-stu-id="8a0c9-184">REF</span></span>  
 <span data-ttu-id="8a0c9-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) erstellt einen Verweis auf eine Instanz eines Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="8a0c9-186">Die folgende Abfrage gibt beispielsweise einen Verweis auf jede Order-Entität in der Orders-Entitätenmenge zurück:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="8a0c9-187">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-187">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-188">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-189">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-189">1</span></span>|  
|<span data-ttu-id="8a0c9-190">2</span><span class="sxs-lookup"><span data-stu-id="8a0c9-190">2</span></span>|  
|<span data-ttu-id="8a0c9-191">3</span><span class="sxs-lookup"><span data-stu-id="8a0c9-191">3</span></span>|  
|<span data-ttu-id="8a0c9-192">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-192">...</span></span>|  
  
 <span data-ttu-id="8a0c9-193">Im folgenden Beispiel wird der Eigenschaftsextrahierungsoperator (.) für den Zugriff auf eine Eigenschaft einer Entität verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="8a0c9-194">Bei der Verwendung des Eigenschaftsextraktionsoperators wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="8a0c9-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="8a0c9-196">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-196">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-197">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8a0c9-198">Adjustable Race</span></span>|  
|<span data-ttu-id="8a0c9-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8a0c9-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8a0c9-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8a0c9-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8a0c9-201">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="8a0c9-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="8a0c9-202">DEREF</span></span>  
 <span data-ttu-id="8a0c9-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="8a0c9-204">Die folgende Abfrage erstellt beispielsweise die Order-Entitäten für jede Bestellung in der Orders-Entitätenmenge: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="8a0c9-205">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="8a0c9-206">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-206">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-207">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8a0c9-208">Adjustable Race</span></span>|  
|<span data-ttu-id="8a0c9-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8a0c9-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8a0c9-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8a0c9-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8a0c9-211">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="8a0c9-212">CREATEREF UND KEY</span><span class="sxs-lookup"><span data-stu-id="8a0c9-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="8a0c9-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) erstellt einen Verweis, der einen Schlüssel übergibt.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="8a0c9-214">[Schlüssel](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrahiert den Schlüsselteil eines Ausdrucks mit Typverweis.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="8a0c9-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="8a0c9-216">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-216">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="8a0c9-218">980</span><span class="sxs-lookup"><span data-stu-id="8a0c9-218">980</span></span>|  
|<span data-ttu-id="8a0c9-219">365</span><span class="sxs-lookup"><span data-stu-id="8a0c9-219">365</span></span>|  
|<span data-ttu-id="8a0c9-220">771</span><span class="sxs-lookup"><span data-stu-id="8a0c9-220">771</span></span>|  
|<span data-ttu-id="8a0c9-221">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="8a0c9-222">Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="8a0c9-223">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-223">Canonical</span></span>  
 <span data-ttu-id="8a0c9-224">Der Namespace für [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) ist Edm, wie in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="8a0c9-225">Der Namespace muss nur dann angegeben werden, wenn ein anderer Namespace importiert wurde, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="8a0c9-226">Wenn zwei Namespaces über die gleiche Funktion verfügen, sollte der Benutzer den vollständigen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="8a0c9-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="8a0c9-228">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-228">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="8a0c9-230">6</span><span class="sxs-lookup"><span data-stu-id="8a0c9-230">6</span></span>|  
|<span data-ttu-id="8a0c9-231">6</span><span class="sxs-lookup"><span data-stu-id="8a0c9-231">6</span></span>|  
|<span data-ttu-id="8a0c9-232">5</span><span class="sxs-lookup"><span data-stu-id="8a0c9-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="8a0c9-233">Microsoft-anbieterspezifische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="8a0c9-234">[Microsoft-anbieterspezifische Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) befinden sich in der `SqlServer` Namespace.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="8a0c9-235">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="8a0c9-236">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-236">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="8a0c9-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="8a0c9-238">27</span><span class="sxs-lookup"><span data-stu-id="8a0c9-238">27</span></span>|  
|<span data-ttu-id="8a0c9-239">27</span><span class="sxs-lookup"><span data-stu-id="8a0c9-239">27</span></span>|  
|<span data-ttu-id="8a0c9-240">26</span><span class="sxs-lookup"><span data-stu-id="8a0c9-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="8a0c9-241">Namespaces</span><span class="sxs-lookup"><span data-stu-id="8a0c9-241">Namespaces</span></span>  
 <span data-ttu-id="8a0c9-242">[Mithilfe von](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) gibt in einem Abfrageausdruck verwendete Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="8a0c9-243">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="8a0c9-244">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-244">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-245">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-246">aa</span><span class="sxs-lookup"><span data-stu-id="8a0c9-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="8a0c9-247">Paging</span><span class="sxs-lookup"><span data-stu-id="8a0c9-247">Paging</span></span>  
 <span data-ttu-id="8a0c9-248">Paging ausgedrückt werden kann, indem Sie deklarieren eine [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) und [Grenzwert](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) Unterklauseln zum der [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="8a0c9-249">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="8a0c9-250">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-250">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-251">ID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-251">ID</span></span>|<span data-ttu-id="8a0c9-252">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="8a0c9-253">10</span><span class="sxs-lookup"><span data-stu-id="8a0c9-253">10</span></span>|<span data-ttu-id="8a0c9-254">Adina</span><span class="sxs-lookup"><span data-stu-id="8a0c9-254">Adina</span></span>|  
|<span data-ttu-id="8a0c9-255">11</span><span class="sxs-lookup"><span data-stu-id="8a0c9-255">11</span></span>|<span data-ttu-id="8a0c9-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="8a0c9-256">Agcaoili</span></span>|  
|<span data-ttu-id="8a0c9-257">12</span><span class="sxs-lookup"><span data-stu-id="8a0c9-257">12</span></span>|<span data-ttu-id="8a0c9-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="8a0c9-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="8a0c9-259">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="8a0c9-259">Grouping</span></span>  
 <span data-ttu-id="8a0c9-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) gibt Gruppen an, in die Objekte, die von einer Abfrage zurückgegebenen ([wählen](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="8a0c9-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="8a0c9-262">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-262">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-263">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-263">name</span></span>|  
|----------|  
|<span data-ttu-id="8a0c9-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8a0c9-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8a0c9-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8a0c9-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8a0c9-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="8a0c9-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="8a0c9-267">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="8a0c9-268">Navigation</span><span class="sxs-lookup"><span data-stu-id="8a0c9-268">Navigation</span></span>  
 <span data-ttu-id="8a0c9-269">Der Beziehungsnavigationsoperator ermöglicht die Navigation der Beziehung von einer Entität (an einem Ende) zu einer anderen Entität (am anderen Ende).</span><span class="sxs-lookup"><span data-stu-id="8a0c9-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="8a0c9-270">[Navigieren Sie](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) nimmt der Beziehungstyp als qualifiziert \<Namespace >.\< Beziehungstypname >.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="8a0c9-271">Navigieren Sie gibt Ref\<T > Wenn die Kardinalität der beenden ist 1.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="8a0c9-272">Wenn die Kardinalität der beenden ist n, die Auflistung < Ref\<T >> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="8a0c9-273">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="8a0c9-274">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-274">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="8a0c9-276">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-276">1</span></span>|  
|<span data-ttu-id="8a0c9-277">2</span><span class="sxs-lookup"><span data-stu-id="8a0c9-277">2</span></span>|  
|<span data-ttu-id="8a0c9-278">3</span><span class="sxs-lookup"><span data-stu-id="8a0c9-278">3</span></span>|  
|<span data-ttu-id="8a0c9-279">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="8a0c9-280">SELECT VALUE UND SELECT</span><span class="sxs-lookup"><span data-stu-id="8a0c9-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="8a0c9-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="8a0c9-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="8a0c9-282"> stellt die SELECT VALUE-Klausel bereit, um die implizite Zeilenkonstruktion zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-282"> provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="8a0c9-283">In einer SELECT VALUE-Klausel kann nur ein Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="8a0c9-284">Wenn diese Klausel wird verwendet, die Elemente in der SELECT-Klausel keine Zeilen-Wrapper erstellt wird und eine Auflistung der gewünschten Form werden, z. B. erstellt kann: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="8a0c9-285">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="8a0c9-286">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-286">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-287">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="8a0c9-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8a0c9-288">Adjustable Race</span></span>|  
|<span data-ttu-id="8a0c9-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8a0c9-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="8a0c9-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8a0c9-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="8a0c9-291">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="8a0c9-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="8a0c9-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="8a0c9-293"> stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-293"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="8a0c9-294">SELECT`SELECT a, b, c` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit Feldern, z. B.: .</span><span class="sxs-lookup"><span data-stu-id="8a0c9-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="8a0c9-295">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-295">Example:</span></span>  
  
 <span data-ttu-id="8a0c9-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="8a0c9-297">Name</span><span class="sxs-lookup"><span data-stu-id="8a0c9-297">Name</span></span>|<span data-ttu-id="8a0c9-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="8a0c9-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="8a0c9-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="8a0c9-299">Adjustable Race</span></span>|<span data-ttu-id="8a0c9-300">1</span><span class="sxs-lookup"><span data-stu-id="8a0c9-300">1</span></span>|  
|<span data-ttu-id="8a0c9-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="8a0c9-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="8a0c9-302">879</span><span class="sxs-lookup"><span data-stu-id="8a0c9-302">879</span></span>|  
|<span data-ttu-id="8a0c9-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="8a0c9-303">AWC Logo Cap</span></span>|<span data-ttu-id="8a0c9-304">712</span><span class="sxs-lookup"><span data-stu-id="8a0c9-304">712</span></span>|  
|<span data-ttu-id="8a0c9-305">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-305">...</span></span>|<span data-ttu-id="8a0c9-306">...</span><span class="sxs-lookup"><span data-stu-id="8a0c9-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="8a0c9-307">CASE EXPRESSION</span><span class="sxs-lookup"><span data-stu-id="8a0c9-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="8a0c9-308">Die [case-Ausdruck](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="8a0c9-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="8a0c9-309">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="8a0c9-310">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8a0c9-310">Output:</span></span>  
  
|<span data-ttu-id="8a0c9-311">Wert</span><span class="sxs-lookup"><span data-stu-id="8a0c9-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="8a0c9-312">true</span><span class="sxs-lookup"><span data-stu-id="8a0c9-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a0c9-313">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a0c9-313">See Also</span></span>  
 [<span data-ttu-id="8a0c9-314">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="8a0c9-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="8a0c9-315">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8a0c9-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
