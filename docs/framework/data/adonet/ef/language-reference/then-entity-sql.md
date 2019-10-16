---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319281"
---
# <a name="then-entity-sql"></a><span data-ttu-id="9d9c5-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9d9c5-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="9d9c5-103">Das Ergebnis einer WHEN-Klausel, wenn sie als `true`ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d9c5-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d9c5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9d9c5-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="9d9c5-106">Jeder gültige boolesche Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="9d9c5-107">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d9c5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d9c5-108">Remarks</span></span>  
 <span data-ttu-id="9d9c5-109">Falls `when_expression` zum Wert `true`ausgewertet wird, ist das Ergebnis der entsprechende `then-expression`.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="9d9c5-110">Wird keine der WHEN-Bedingungen erfüllt, wird der `else-expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="9d9c5-111">Wenn jedoch kein `else-expression`vorhanden ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="9d9c5-112">Ein Beispiel finden Sie unter [Case](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9d9c5-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d9c5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d9c5-113">Example</span></span>  
 <span data-ttu-id="9d9c5-114">In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung einer Reihe von `Boolean` -Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="9d9c5-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="9d9c5-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9d9c5-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="9d9c5-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9d9c5-117">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9d9c5-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="9d9c5-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="9d9c5-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="9d9c5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d9c5-119">See also</span></span>

- [<span data-ttu-id="9d9c5-120">CASE</span><span class="sxs-lookup"><span data-stu-id="9d9c5-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="9d9c5-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9d9c5-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
