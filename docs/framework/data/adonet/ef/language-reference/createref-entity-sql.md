---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: cbaea82108dd3debcca972ca15dea248227330ac
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251106"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="0f768-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0f768-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="0f768-103">Erstellt Verweise auf eine Entität in einer Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="0f768-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f768-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f768-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f768-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0f768-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="0f768-106">Der Entitätenmengenbezeichner, kein Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="0f768-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="0f768-107">Ein zeilentypisierter Ausdruck, der den Schlüsseleigenschaften des Entitätstyps entspricht.</span><span class="sxs-lookup"><span data-stu-id="0f768-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f768-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f768-108">Remarks</span></span>  
 <span data-ttu-id="0f768-109">`row_typed_expression` muss strukturell dem Schlüsseltyp der Entität entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0f768-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="0f768-110">Dies bedeutet, er muss hinsichtlich Anzahl, Typen und Reihenfolge der Felder zu den Entitätsschlüsseln passen.</span><span class="sxs-lookup"><span data-stu-id="0f768-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="0f768-111">Im folgenden Beispiel sind sowohl "Orders" als auch "BadOrders" Entitätenmengen vom Typ "Order". "Id" ist die einzige Schlüsseleigenschaft von "Order".</span><span class="sxs-lookup"><span data-stu-id="0f768-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="0f768-112">Im Beispiel wird veranschaulicht, wie in "BadOrders" ein Verweis auf eine Entität erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f768-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="0f768-113">Beachten Sie, dass der Verweis möglicherweise „hängt“.</span><span class="sxs-lookup"><span data-stu-id="0f768-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="0f768-114">Dies bedeutet, dass der Verweis möglicherweise keine spezifische Entität identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0f768-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="0f768-115">In diesen Fällen gibt eine `DEREF` -Operation auf diesen Verweis den Wert NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="0f768-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="0f768-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f768-116">Example</span></span>  
 <span data-ttu-id="0f768-117">In der folgenden Entity SQL-Abfrage werden mithilfe des CREATEREF-Operators Verweise auf eine Entität in einer Entitätenmenge erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f768-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="0f768-118">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="0f768-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0f768-119">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="0f768-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0f768-120">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0f768-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0f768-121">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="0f768-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="0f768-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f768-122">See also</span></span>

- [<span data-ttu-id="0f768-123">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="0f768-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="0f768-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="0f768-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="0f768-125">KEY</span><span class="sxs-lookup"><span data-stu-id="0f768-125">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="0f768-126">REF</span><span class="sxs-lookup"><span data-stu-id="0f768-126">REF</span></span>](ref-entity-sql.md)
