---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: df86e69684a111effc29a2663d18310b276f4b83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="case-entity-sql"></a><span data-ttu-id="cd028-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cd028-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="cd028-103">Wertet eine Reihe von `Boolean` -Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cd028-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd028-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd028-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="cd028-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cd028-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="cd028-106">Ist ein Platzhalter, der angibt, dass mehrere WHEN `Boolean_expression` THEN `result_expression` -Klauseln verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cd028-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="cd028-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="cd028-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="cd028-108">Ist der zurückgegebene Ausdruck, wenn `Boolean_expression` den Wert `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="cd028-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="cd028-109">`result expression` ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="cd028-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="cd028-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="cd028-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="cd028-111">Der Ausdruck, der zurückgegeben wird, wenn keine Vergleichsoperation `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="cd028-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="cd028-112">Wenn dieses Argument nicht angegeben wird und keine Vergleichsoperation `true`ergibt, gibt die CASE-Funktion null zurück.</span><span class="sxs-lookup"><span data-stu-id="cd028-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="cd028-113">`else_result_expression` ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="cd028-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="cd028-114">Die Datentypen von `else_result_expression` und allen `result_expression` -Ausdrücken müssen gleich sein, oder es muss eine implizite Konvertierung vorliegen.</span><span class="sxs-lookup"><span data-stu-id="cd028-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="cd028-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="cd028-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="cd028-116">Der `Boolean` -Ausdruck, der ausgewertet wird, wenn das gesuchte CASE-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd028-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="cd028-117">`Boolean_expression` ist ein beliebiger gültiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="cd028-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd028-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd028-118">Return Value</span></span>  
 <span data-ttu-id="cd028-119">Gibt den Typ mit der höchsten Priorität in `result_expression` und im optionalen `else_result_expression`zurück.</span><span class="sxs-lookup"><span data-stu-id="cd028-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd028-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd028-120">Remarks</span></span>  
 <span data-ttu-id="cd028-121">Der CASE-Ausdruck von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt dem CASE-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd028-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="cd028-122">Mit dem CASE-Ausdruck wird eine Reihe von Bedingungen geprüft, um zu ermitteln, welcher Ausdruck das passende Ergebnis ergibt.</span><span class="sxs-lookup"><span data-stu-id="cd028-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="cd028-123">Diese Form des CASE-Ausdrucks ist für einen oder eine Reihe von `Boolean` -Ausdrücken geeignet, um den korrekten Ergebnisausdruck zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cd028-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="cd028-124">Die CASE-Funktion wertet `Boolean_expression` für jede WHEN-Klausel in der angegebenen Reihenfolge aus und gibt `result_expression` des ersten `Boolean_expression` zurück, der `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="cd028-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="cd028-125">Die übrigen Ausdrücke werden nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cd028-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="cd028-126">Ergibt kein `Boolean_expression` den Wert `true`, gibt das Datenbankmodul den `else_result_expression` -Ausdruck zurück, sofern eine ELSE-Klausel angegeben wurde, oder einen NULL-Wert, wenn keine ELSE-Klausel angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cd028-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="cd028-127">Eine CASE-Anweisung kann keinen multiset-Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cd028-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd028-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd028-128">Example</span></span>  
 <span data-ttu-id="cd028-129">In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung eines Satzes von `Boolean` -Ausdrücken verwendet, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cd028-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="cd028-130">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="cd028-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cd028-131">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cd028-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cd028-132">Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cd028-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="cd028-133">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="cd028-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="cd028-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd028-134">See Also</span></span>  
 [<span data-ttu-id="cd028-135">THEN</span><span class="sxs-lookup"><span data-stu-id="cd028-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="cd028-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="cd028-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="cd028-137">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="cd028-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
