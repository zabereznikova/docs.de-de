---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: bab31ca0a6fd37f5179412b7a4936d564620135e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761769"
---
# <a name="between-entity-sql"></a><span data-ttu-id="8ea18-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8ea18-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="8ea18-103">Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="8ea18-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="8ea18-104">Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie die Transact-SQL BETWEEN-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8ea18-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea18-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ea18-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="8ea18-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="8ea18-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8ea18-107">Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8ea18-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="8ea18-108">`expression` muss den gleichen Typ wie `begin_expression` und `end_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8ea18-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="8ea18-109">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8ea18-109">Any valid expression.</span></span> <span data-ttu-id="8ea18-110">`begin_expression` muss den gleichen Typ wie `expression` und `end_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8ea18-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="8ea18-111">`begin_expression` sollte kleiner als `end_expression` sein, anderenfalls wird der Rückgabewert negiert.</span><span class="sxs-lookup"><span data-stu-id="8ea18-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="8ea18-112">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8ea18-112">Any valid expression.</span></span> <span data-ttu-id="8ea18-113">`end_expression` muss den gleichen Typ wie `expression` und `begin_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8ea18-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="8ea18-114">NOT</span><span class="sxs-lookup"><span data-stu-id="8ea18-114">NOT</span></span>  
 <span data-ttu-id="8ea18-115">Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ea18-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="8ea18-116">AND</span><span class="sxs-lookup"><span data-stu-id="8ea18-116">AND</span></span>  
 <span data-ttu-id="8ea18-117">Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.</span><span class="sxs-lookup"><span data-stu-id="8ea18-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ea18-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8ea18-118">Return Value</span></span>  
 <span data-ttu-id="8ea18-119">`true`, wenn `expression` in dem von `begin_expression` und `end_expression` angegebenen Bereich liegt, anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8ea18-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="8ea18-120">`null` wird zurückgegeben, wenn `expression` entweder `null` ist, oder wenn `begin_expression` oder `end_expression` den Wert `null` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8ea18-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ea18-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ea18-121">Remarks</span></span>  
 <span data-ttu-id="8ea18-122">Zum Angeben eines Bereichs, der seine Grenzen nicht enthält, sollten anstelle des BETWEEN-Operators die Operatoren "Größer-als" (>) und "Kleiner-als" (<) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea18-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea18-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ea18-123">Example</span></span>  
 <span data-ttu-id="8ea18-124">In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="8ea18-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="8ea18-125">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="8ea18-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8ea18-126">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="8ea18-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8ea18-127">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8ea18-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="8ea18-128">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="8ea18-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="8ea18-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea18-129">See Also</span></span>  
 [<span data-ttu-id="8ea18-130">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="8ea18-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
