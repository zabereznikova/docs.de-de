---
title: UNION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b62d874a9885ed864282c765cf428f3c2a445745
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="union-entity-sql"></a><span data-ttu-id="d8886-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d8886-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="d8886-103">Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="d8886-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8886-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8886-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8886-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d8886-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d8886-106">Jeder gültige Abfrageausdruck, der eine mit der Auflistung zusammenzufassende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`sein.</span><span class="sxs-lookup"><span data-stu-id="d8886-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="d8886-107">UNION</span><span class="sxs-lookup"><span data-stu-id="d8886-107">UNION</span></span>  
 <span data-ttu-id="d8886-108">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d8886-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="d8886-109">ALL</span><span class="sxs-lookup"><span data-stu-id="d8886-109">ALL</span></span>  
 <span data-ttu-id="d8886-110">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen, wobei Duplikate erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="d8886-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="d8886-111">Wenn dies nicht angegeben wird, werden Duplikate aus der Ergebnisauflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="d8886-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8886-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d8886-112">Return Value</span></span>  
 <span data-ttu-id="d8886-113">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="d8886-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8886-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8886-114">Remarks</span></span>  
 <span data-ttu-id="d8886-115">UNION ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="d8886-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d8886-116">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="d8886-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d8886-117">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren, finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d8886-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8886-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8886-118">Example</span></span>  
 <span data-ttu-id="d8886-119">Die folgende Entity SQL-Abfrage verwendet den UNION ALL-Operator, um die Ergebnisse von zwei Abfragen in einer Auflistung zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="d8886-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="d8886-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d8886-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d8886-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d8886-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d8886-122">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d8886-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d8886-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d8886-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="d8886-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8886-124">See Also</span></span>  
 [<span data-ttu-id="d8886-125">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d8886-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
