---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 3360ad4ca7306a8cc1b7d6948204f825ff9a93c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203617"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="59a50-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="59a50-102">ISNULL (Entity SQL)</span></span>

<span data-ttu-id="59a50-103">Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.</span><span class="sxs-lookup"><span data-stu-id="59a50-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59a50-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="59a50-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="59a50-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="59a50-106">Ein gültiger Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="59a50-106">Any valid query expression.</span></span> <span data-ttu-id="59a50-107">Dieser darf keine Auflistung sein oder über Auflistungsmember oder einen Datensatztyp mit Auflistungstypeigenschaften verfügen.</span><span class="sxs-lookup"><span data-stu-id="59a50-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="59a50-108">NICHT</span><span class="sxs-lookup"><span data-stu-id="59a50-108">NOT</span></span>  
 <span data-ttu-id="59a50-109">Negiert das EDM.Boolean-Ergebnis von IS NULL.</span><span class="sxs-lookup"><span data-stu-id="59a50-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59a50-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="59a50-110">Return Value</span></span>  

 <span data-ttu-id="59a50-111">`true` wenn `expression` NULL zurückgibt, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="59a50-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59a50-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="59a50-112">Remarks</span></span>  

 <span data-ttu-id="59a50-113">Verwenden Sie `IS NULL`, um zu ermitteln, ob das Element einer äußeren Verknüpfung den Wert NULL hat:</span><span class="sxs-lookup"><span data-stu-id="59a50-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="59a50-114">Verwenden Sie `IS NULL`, um zu ermitteln, ob ein Member über einen tatsächlichen Wert verfügt:</span><span class="sxs-lookup"><span data-stu-id="59a50-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="59a50-115">In der folgenden Tabelle wird das Verhalten von `IS NULL` für einige Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="59a50-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="59a50-116">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="59a50-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="59a50-117">Muster</span><span class="sxs-lookup"><span data-stu-id="59a50-117">Pattern</span></span>|<span data-ttu-id="59a50-118">Verhalten</span><span class="sxs-lookup"><span data-stu-id="59a50-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="59a50-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-119">null IS NULL</span></span>|<span data-ttu-id="59a50-120">Gibt `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="59a50-120">Returns `true`.</span></span>|  
|<span data-ttu-id="59a50-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="59a50-122">Gibt `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="59a50-122">Returns `true`.</span></span>|  
|<span data-ttu-id="59a50-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="59a50-124">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="59a50-124">Throws an error.</span></span>|  
|<span data-ttu-id="59a50-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="59a50-126">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="59a50-126">Throws an error.</span></span>|  
|<span data-ttu-id="59a50-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-127">EntityType IS NULL</span></span>|<span data-ttu-id="59a50-128">Gibt einen `true` oder `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="59a50-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="59a50-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-129">ComplexType IS NULL</span></span>|<span data-ttu-id="59a50-130">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="59a50-130">Throws an error.</span></span>|  
|<span data-ttu-id="59a50-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="59a50-131">RowType IS NULL</span></span>|<span data-ttu-id="59a50-132">Löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="59a50-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59a50-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59a50-133">Example</span></span>  

 <span data-ttu-id="59a50-134">In der folgenden- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage wird der is not NULL-Operator verwendet, um zu bestimmen, ob ein Abfrage Ausdruck nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="59a50-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="59a50-135">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="59a50-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="59a50-136">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="59a50-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="59a50-137">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="59a50-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="59a50-138">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="59a50-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="59a50-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59a50-139">See also</span></span>

- [<span data-ttu-id="59a50-140">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="59a50-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
