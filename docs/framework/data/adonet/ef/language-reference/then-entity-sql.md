---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 8d2d7f9a3a1d6ff9f25db3f19bf8f39781469f9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305623"
---
# <a name="then-entity-sql"></a><span data-ttu-id="f613d-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f613d-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="f613d-103">Das Ergebnis einer WHEN-Klausel, wenn sie als `true`ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="f613d-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f613d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f613d-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f613d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f613d-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="f613d-106">Jeder gültige boolesche Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f613d-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="f613d-107">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f613d-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f613d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f613d-108">Remarks</span></span>  
 <span data-ttu-id="f613d-109">Falls `when_expression` zum Wert `true`ausgewertet wird, ist das Ergebnis der entsprechende `then-expression`.</span><span class="sxs-lookup"><span data-stu-id="f613d-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="f613d-110">Wird keine der WHEN-Bedingungen erfüllt, wird der `else-expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f613d-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="f613d-111">Wenn jedoch kein `else-expression`vorhanden ist, ist das Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="f613d-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="f613d-112">Ein Beispiel finden Sie unter [Fall](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f613d-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f613d-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f613d-113">Example</span></span>  
 <span data-ttu-id="f613d-114">In der folgenden Entity SQL-Abfrage wird der CASE-Ausdruck zur Auswertung einer Reihe von `Boolean` -Ausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="f613d-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="f613d-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="f613d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f613d-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f613d-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f613d-117">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f613d-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f613d-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="f613d-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="f613d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f613d-119">See also</span></span>

- [<span data-ttu-id="f613d-120">CASE</span><span class="sxs-lookup"><span data-stu-id="f613d-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [<span data-ttu-id="f613d-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="f613d-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
