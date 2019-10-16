---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: dc7338d176302b8683d541ab0dc715dd8d149c6f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319768"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="495e1-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="495e1-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="495e1-103">Gibt eine Auflistung aller unterschiedlicher Werte zurück, die sowohl vom Abfrageausdruck auf der linken als auch dem auf der rechten Seite des INTERSECT-Operands zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="495e1-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="495e1-104">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="495e1-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="495e1-105">Syntax</span></span>  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="495e1-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="495e1-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="495e1-107">Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="495e1-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="495e1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="495e1-108">Return Value</span></span>  
 <span data-ttu-id="495e1-109">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="495e1-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="495e1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="495e1-110">Remarks</span></span>  
 <span data-ttu-id="495e1-111">INTERSECT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="495e1-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="495e1-112">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="495e1-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="495e1-113">Informationen zu Rang folgen Informationen für die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="495e1-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="495e1-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="495e1-114">Example</span></span>  
 <span data-ttu-id="495e1-115">In der folgenden Entity SQL-Abfrage wird der INTERSECT-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte zurückzugeben, die von beiden Abfrageausdrücken auf der linken und der rechten Seite des INTERSECT-Operators zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="495e1-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="495e1-116">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="495e1-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="495e1-117">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="495e1-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="495e1-118">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="495e1-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="495e1-119">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="495e1-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="495e1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="495e1-120">See also</span></span>

- [<span data-ttu-id="495e1-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="495e1-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
