---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: c90950e11cbfca7a49b505c1654d08be504990e1
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46507317"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="9cb32-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9cb32-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="9cb32-103">Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="9cb32-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cb32-104">Syntax</span></span>  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="9cb32-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9cb32-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9cb32-106">Jeder gültige Abfrageausdruck, der eine Auflistung von Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9cb32-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="9cb32-107">Der Typ, dessen Übereinstimmung mit jedem von `expression` zurückgegebenen Objekt getestet wird.</span><span class="sxs-lookup"><span data-stu-id="9cb32-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="9cb32-108">Der Typ muss mit einem Namespace qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="9cb32-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cb32-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9cb32-109">Return Value</span></span>  
 <span data-ttu-id="9cb32-110">Eine Auflistung von Objekten vom Typ `test_type`, von einem Basistyp oder von einem von `test_type`abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="9cb32-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="9cb32-111">Wenn ONLY angegeben wird, werden nur Instanzen des `test_type` oder eine leere Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cb32-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cb32-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cb32-112">Remarks</span></span>  
 <span data-ttu-id="9cb32-113">Ein `OFTYPE` -Ausdruck stellt einen Typausdruck dar, der angegeben wird, um einen Typtest für jedes Element einer Auflistung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9cb32-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="9cb32-114">Der `OFTYPE` -Ausdruck liefert eine neue Auflistung des angegebenen Typs, die nur die zu diesem Typ oder einem seiner Untertypen äquivalenten Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="9cb32-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="9cb32-115">Ein `OFTYPE` -Ausdruck ist eine Abkürzung des folgenden Abfrageausdrucks:</span><span class="sxs-lookup"><span data-stu-id="9cb32-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="9cb32-116">Wenn beispielsweise "Manager" ein Untertyp von "Employee" (Mitarbeiter) ist, liefert der folgende Ausdruck nur die Manager aus einer Auflistung der Mitarbeiter:</span><span class="sxs-lookup"><span data-stu-id="9cb32-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="9cb32-117">Mithilfe des Typfilters kann eine Auflistung auch umgewandelt werden:</span><span class="sxs-lookup"><span data-stu-id="9cb32-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="9cb32-118">Da alle Direktoren Manager sind, enthält die resultierende Auflistung alle Direktoren, auch wenn die Auflistung nun als eine Auflistung von Managern typisiert ist.</span><span class="sxs-lookup"><span data-stu-id="9cb32-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="9cb32-119">In der folgenden Tabelle wird das Verhalten des `OFTYPE` -Operators für verschiedene Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9cb32-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="9cb32-120">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="9cb32-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="9cb32-121">Muster</span><span class="sxs-lookup"><span data-stu-id="9cb32-121">Pattern</span></span>|<span data-ttu-id="9cb32-122">Verhalten</span><span class="sxs-lookup"><span data-stu-id="9cb32-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="9cb32-123">OFTYPE (Collection(EntityType), (EntityType)</span><span class="sxs-lookup"><span data-stu-id="9cb32-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="9cb32-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="9cb32-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="9cb32-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="9cb32-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="9cb32-126">Löst aus</span><span class="sxs-lookup"><span data-stu-id="9cb32-126">Throws</span></span>|  
|<span data-ttu-id="9cb32-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="9cb32-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="9cb32-128">Löst aus</span><span class="sxs-lookup"><span data-stu-id="9cb32-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9cb32-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cb32-129">Example</span></span>  
 <span data-ttu-id="9cb32-130">Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage verwendet den OFTYPE-Operator, um eine Auflistung der OnsiteCourse-Objekte von einer Auflistung von Kursobjekten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9cb32-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="9cb32-131">Die Abfrage basiert auf der [Modell "School"](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="9cb32-131">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="9cb32-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cb32-132">See Also</span></span>  
 [<span data-ttu-id="9cb32-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9cb32-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
