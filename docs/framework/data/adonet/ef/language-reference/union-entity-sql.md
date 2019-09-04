---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 34eac0dfd28d39ec68f084ea10dd46693f44eea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248791"
---
# <a name="union-entity-sql"></a><span data-ttu-id="2cbc8-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2cbc8-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="2cbc8-103">Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cbc8-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cbc8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2cbc8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2cbc8-106">Jeder gültige Abfrageausdruck, der eine mit der Auflistung zusammenzufassende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`sein.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="2cbc8-107">UNION</span><span class="sxs-lookup"><span data-stu-id="2cbc8-107">UNION</span></span>  
 <span data-ttu-id="2cbc8-108">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="2cbc8-109">ALL</span><span class="sxs-lookup"><span data-stu-id="2cbc8-109">ALL</span></span>  
 <span data-ttu-id="2cbc8-110">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen, wobei Duplikate erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="2cbc8-111">Wenn dies nicht angegeben wird, werden Duplikate aus der Ergebnisauflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cbc8-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2cbc8-112">Return Value</span></span>  
 <span data-ttu-id="2cbc8-113">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cbc8-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cbc8-114">Remarks</span></span>  
 <span data-ttu-id="2cbc8-115">UNION ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="2cbc8-116">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="2cbc8-117">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbc8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cbc8-118">Example</span></span>  
 <span data-ttu-id="2cbc8-119">Die folgende Entity SQL-Abfrage verwendet den UNION ALL-Operator, um die Ergebnisse von zwei Abfragen in einer Auflistung zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="2cbc8-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2cbc8-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2cbc8-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2cbc8-122">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2cbc8-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2cbc8-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="2cbc8-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="2cbc8-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cbc8-124">See also</span></span>

- [<span data-ttu-id="2cbc8-125">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="2cbc8-125">Entity SQL Reference</span></span>](entity-sql-reference.md)
