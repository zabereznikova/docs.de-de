---
title: BETWEEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3b27aee261e9195c2cb5f15e369cf26de4c0691a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="between-entity-sql"></a><span data-ttu-id="e7108-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7108-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="e7108-103">Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="e7108-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e7108-104">Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie die Transact-SQL BETWEEN-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7108-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7108-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7108-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="e7108-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="e7108-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e7108-107">Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e7108-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="e7108-108">`expression` muss den gleichen Typ wie `begin_expression` und `end_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7108-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="e7108-109">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7108-109">Any valid expression.</span></span> <span data-ttu-id="e7108-110">`begin_expression` muss den gleichen Typ wie `expression` und `end_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7108-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="e7108-111">`begin_expression` sollte kleiner als `end_expression` sein, anderenfalls wird der Rückgabewert negiert.</span><span class="sxs-lookup"><span data-stu-id="e7108-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="e7108-112">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7108-112">Any valid expression.</span></span> <span data-ttu-id="e7108-113">`end_expression` muss den gleichen Typ wie `expression` und `begin_expression` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7108-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="e7108-114">NOT</span><span class="sxs-lookup"><span data-stu-id="e7108-114">NOT</span></span>  
 <span data-ttu-id="e7108-115">Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7108-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="e7108-116">AND</span><span class="sxs-lookup"><span data-stu-id="e7108-116">AND</span></span>  
 <span data-ttu-id="e7108-117">Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.</span><span class="sxs-lookup"><span data-stu-id="e7108-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7108-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7108-118">Return Value</span></span>  
 <span data-ttu-id="e7108-119">`true`, wenn `expression` in dem von `begin_expression` und `end_expression` angegebenen Bereich liegt, anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e7108-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="e7108-120">`null` wird zurückgegeben, wenn `expression` entweder `null` ist, oder wenn `begin_expression` oder `end_expression` den Wert `null` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7108-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7108-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7108-121">Remarks</span></span>  
 <span data-ttu-id="e7108-122">Zum Angeben eines Bereichs, der seine Grenzen nicht enthält, sollten anstelle des BETWEEN-Operators die Operatoren "Größer-als" (>) und "Kleiner-als" (<) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7108-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7108-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7108-123">Example</span></span>  
 <span data-ttu-id="e7108-124">In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="e7108-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e7108-125">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="e7108-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e7108-126">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e7108-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e7108-127">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e7108-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e7108-128">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="e7108-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="e7108-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7108-129">See Also</span></span>  
 [<span data-ttu-id="e7108-130">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="e7108-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
