---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: a943de89de37d00cc2a643b443da7ef1fd3380b9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250604"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="9b27f-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9b27f-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="9b27f-103">Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b27f-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="9b27f-104">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="9b27f-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b27f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b27f-105">Syntax</span></span>  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b27f-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="9b27f-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9b27f-107">Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9b27f-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b27f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b27f-108">Return Value</span></span>  
 <span data-ttu-id="9b27f-109">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="9b27f-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b27f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b27f-110">Remarks</span></span>  
 <span data-ttu-id="9b27f-111">INTERSECT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="9b27f-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="9b27f-112">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9b27f-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="9b27f-113">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="9b27f-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b27f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b27f-114">Example</span></span>  
 <span data-ttu-id="9b27f-115">In der folgenden Entity SQL-Abfrage wird der INTERSECT-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte zurückzugeben, die von beiden Abfrageausdrücken auf der linken und der rechten Seite des INTERSECT-Operators zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9b27f-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="9b27f-116">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="9b27f-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9b27f-117">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="9b27f-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9b27f-118">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9b27f-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9b27f-119">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="9b27f-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="9b27f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b27f-120">See also</span></span>

- [<span data-ttu-id="9b27f-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9b27f-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
