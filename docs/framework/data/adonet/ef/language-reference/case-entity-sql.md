---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: e44f48d040fc77bf702759be0c53a618cd84f9fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334886"
---
# <a name="case-entity-sql"></a><span data-ttu-id="6fa7e-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6fa7e-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="6fa7e-103">Wertet eine Reihe von `Boolean` -Ausdrücken aus, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fa7e-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="6fa7e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6fa7e-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="6fa7e-106">Ist ein Platzhalter, der angibt, dass mehrere WHEN `Boolean_expression` THEN `result_expression` -Klauseln verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="6fa7e-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="6fa7e-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="6fa7e-108">Ist der zurückgegebene Ausdruck, wenn `Boolean_expression` den Wert `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="6fa7e-109">`result expression` ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="6fa7e-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="6fa7e-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="6fa7e-111">Der Ausdruck, der zurückgegeben wird, wenn keine Vergleichsoperation `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="6fa7e-112">Wenn dieses Argument nicht angegeben wird und keine Vergleichsoperation `true`ergibt, gibt die CASE-Funktion null zurück.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="6fa7e-113">`else_result_expression` ist ein beliebiger gültiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="6fa7e-114">Die Datentypen von `else_result_expression` und allen `result_expression` -Ausdrücken müssen gleich sein, oder es muss eine implizite Konvertierung vorliegen.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="6fa7e-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="6fa7e-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="6fa7e-116">Der `Boolean` -Ausdruck, der ausgewertet wird, wenn das gesuchte CASE-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="6fa7e-117">`Boolean_expression` ist ein beliebiger gültiger `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fa7e-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6fa7e-118">Return Value</span></span>  
 <span data-ttu-id="6fa7e-119">Gibt den Typ mit der höchsten Priorität in `result_expression` und im optionalen `else_result_expression`zurück.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fa7e-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fa7e-120">Remarks</span></span>  
 <span data-ttu-id="6fa7e-121">Der CASE-Ausdruck von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt dem CASE-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fa7e-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="6fa7e-122">Mit dem CASE-Ausdruck wird eine Reihe von Bedingungen geprüft, um zu ermitteln, welcher Ausdruck das passende Ergebnis ergibt.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="6fa7e-123">Diese Form des CASE-Ausdrucks ist für einen oder eine Reihe von `Boolean` -Ausdrücken geeignet, um den korrekten Ergebnisausdruck zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="6fa7e-124">Die CASE-Funktion wertet `Boolean_expression` für jede WHEN-Klausel in der angegebenen Reihenfolge aus und gibt `result_expression` des ersten `Boolean_expression` zurück, der `true`ergibt.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="6fa7e-125">Die übrigen Ausdrücke werden nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="6fa7e-126">Ergibt kein `Boolean_expression` den Wert `true`, gibt die Datenbank-Engine den `else_result_expression` -Ausdruck zurück, sofern eine ELSE-Klausel angegeben wurde, oder einen NULL-Wert, wenn keine ELSE-Klausel angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="6fa7e-127">Eine CASE-Anweisung kann keinen multiset-Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fa7e-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fa7e-128">Example</span></span>  
 <span data-ttu-id="6fa7e-129">In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung eines Satzes von `Boolean` -Ausdrücken verwendet, um das Ergebnis zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="6fa7e-130">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="6fa7e-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6fa7e-131">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="6fa7e-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6fa7e-132">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6fa7e-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="6fa7e-133">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="6fa7e-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="6fa7e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fa7e-134">See also</span></span>

- [<span data-ttu-id="6fa7e-135">THEN</span><span class="sxs-lookup"><span data-stu-id="6fa7e-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)
- [<span data-ttu-id="6fa7e-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="6fa7e-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [<span data-ttu-id="6fa7e-137">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6fa7e-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
