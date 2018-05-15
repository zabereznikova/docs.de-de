---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 44954dcc1f3407a768ba23fe87ac4b4abcf1bac5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="createref-entity-sql"></a><span data-ttu-id="47c9e-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="47c9e-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="47c9e-103">Erstellt Verweise auf eine Entität in einer Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="47c9e-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47c9e-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="47c9e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="47c9e-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="47c9e-106">Der Entitätenmengenbezeichner, kein Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="47c9e-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="47c9e-107">Ein zeilentypisierter Ausdruck, der den Schlüsseleigenschaften des Entitätstyps entspricht.</span><span class="sxs-lookup"><span data-stu-id="47c9e-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47c9e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47c9e-108">Remarks</span></span>  
 <span data-ttu-id="47c9e-109">`row_typed_expression` muss strukturell dem Schlüsseltyp der Entität entsprechen.</span><span class="sxs-lookup"><span data-stu-id="47c9e-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="47c9e-110">Dies bedeutet, er muss hinsichtlich Anzahl, Typen und Reihenfolge der Felder zu den Entitätsschlüsseln passen.</span><span class="sxs-lookup"><span data-stu-id="47c9e-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="47c9e-111">Im folgenden Beispiel sind sowohl "Orders" als auch "BadOrders" Entitätenmengen vom Typ "Order". "Id" ist die einzige Schlüsseleigenschaft von "Order".</span><span class="sxs-lookup"><span data-stu-id="47c9e-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="47c9e-112">Im Beispiel wird veranschaulicht, wie in "BadOrders" ein Verweis auf eine Entität erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="47c9e-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="47c9e-113">Beachten Sie, dass der Verweis möglicherweise „hängt“.</span><span class="sxs-lookup"><span data-stu-id="47c9e-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="47c9e-114">Dies bedeutet, dass der Verweis möglicherweise keine spezifische Entität identifiziert.</span><span class="sxs-lookup"><span data-stu-id="47c9e-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="47c9e-115">In diesen Fällen gibt eine `DEREF` -Operation auf diesen Verweis den Wert NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="47c9e-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="47c9e-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47c9e-116">Example</span></span>  
 <span data-ttu-id="47c9e-117">In der folgenden Entity SQL-Abfrage werden mithilfe des CREATEREF-Operators Verweise auf eine Entität in einer Entitätenmenge erstellt.</span><span class="sxs-lookup"><span data-stu-id="47c9e-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="47c9e-118">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="47c9e-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="47c9e-119">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="47c9e-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="47c9e-120">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="47c9e-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="47c9e-121">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="47c9e-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="47c9e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c9e-122">See Also</span></span>  
 [<span data-ttu-id="47c9e-123">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="47c9e-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="47c9e-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="47c9e-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="47c9e-125">KEY</span><span class="sxs-lookup"><span data-stu-id="47c9e-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="47c9e-126">REF</span><span class="sxs-lookup"><span data-stu-id="47c9e-126">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
