---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: d54c350196ad1ef7cfafa6d931d9d1ad8f267177
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250554"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="43d81-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="43d81-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="43d81-103">Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.</span><span class="sxs-lookup"><span data-stu-id="43d81-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43d81-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="43d81-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="43d81-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="43d81-106">Ein gültiger Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="43d81-106">Any valid query expression.</span></span> <span data-ttu-id="43d81-107">Dieser darf keine Auflistung sein oder über Auflistungsmember oder einen Datensatztyp mit Auflistungstypeigenschaften verfügen.</span><span class="sxs-lookup"><span data-stu-id="43d81-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="43d81-108">NICHT</span><span class="sxs-lookup"><span data-stu-id="43d81-108">NOT</span></span>  
 <span data-ttu-id="43d81-109">Negiert das EDM.Boolean-Ergebnis von IS NULL.</span><span class="sxs-lookup"><span data-stu-id="43d81-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43d81-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="43d81-110">Return Value</span></span>  
 <span data-ttu-id="43d81-111">`true` wenn `expression` NULL zurückgibt, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="43d81-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d81-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43d81-112">Remarks</span></span>  
 <span data-ttu-id="43d81-113">Verwenden Sie `IS NULL`, um zu ermitteln, ob das Element einer äußeren Verknüpfung den Wert NULL hat:</span><span class="sxs-lookup"><span data-stu-id="43d81-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="43d81-114">Verwenden Sie `IS NULL`, um zu ermitteln, ob ein Member über einen tatsächlichen Wert verfügt:</span><span class="sxs-lookup"><span data-stu-id="43d81-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="43d81-115">In der folgenden Tabelle wird das Verhalten von `IS NULL` für einige Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="43d81-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="43d81-116">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="43d81-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="43d81-117">Muster</span><span class="sxs-lookup"><span data-stu-id="43d81-117">Pattern</span></span>|<span data-ttu-id="43d81-118">Verhalten</span><span class="sxs-lookup"><span data-stu-id="43d81-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="43d81-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-119">null IS NULL</span></span>|<span data-ttu-id="43d81-120">Gibt `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="43d81-120">Returns `true`.</span></span>|  
|<span data-ttu-id="43d81-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="43d81-122">Gibt `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="43d81-122">Returns `true`.</span></span>|  
|<span data-ttu-id="43d81-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="43d81-124">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="43d81-124">Throws an error.</span></span>|  
|<span data-ttu-id="43d81-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="43d81-126">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="43d81-126">Throws an error.</span></span>|  
|<span data-ttu-id="43d81-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-127">EntityType IS NULL</span></span>|<span data-ttu-id="43d81-128">Gibt einen `true` oder `false`zurück.</span><span class="sxs-lookup"><span data-stu-id="43d81-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="43d81-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-129">ComplexType IS NULL</span></span>|<span data-ttu-id="43d81-130">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="43d81-130">Throws an error.</span></span>|  
|<span data-ttu-id="43d81-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="43d81-131">RowType IS NULL</span></span>|<span data-ttu-id="43d81-132">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="43d81-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="43d81-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43d81-133">Example</span></span>  
 <span data-ttu-id="43d81-134">In der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] folgenden-Abfrage wird der is not NULL-Operator verwendet, um zu bestimmen, ob ein Abfrage Ausdruck nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="43d81-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="43d81-135">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="43d81-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="43d81-136">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="43d81-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="43d81-137">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="43d81-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="43d81-138">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="43d81-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="43d81-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43d81-139">See also</span></span>

- [<span data-ttu-id="43d81-140">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="43d81-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
