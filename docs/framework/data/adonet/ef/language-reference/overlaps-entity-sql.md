---
title: OVERLAPS (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3544eac58fe168c5f2e6a355e8cf97b4598bb76
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="ecdaa-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ecdaa-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="ecdaa-103">Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdaa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecdaa-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ecdaa-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ecdaa-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ecdaa-106">Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="ecdaa-107">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecdaa-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ecdaa-108">Return Value</span></span>  
 <span data-ttu-id="ecdaa-109">`true` , wenn die beiden Auflistungen gemeinsame Elemente aufweisen, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecdaa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecdaa-110">Remarks</span></span>  
 <span data-ttu-id="ecdaa-111">OVERLAPS bereitgestellten Funktionen entspricht der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ecdaa-111">OVERLAPS provides functionally equivalent tothe following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="ecdaa-112">OVERLAPS ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ecdaa-113">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ecdaa-114">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren, finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ecdaa-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecdaa-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecdaa-115">Example</span></span>  
 <span data-ttu-id="ecdaa-116">Die folgende Entity SQL-Abfrage verwendet den OVERLAPS-Operator, um zu bestimmen, ob zwei Auflistungen einen gemeinsamen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="ecdaa-117">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="ecdaa-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ecdaa-118">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ecdaa-118">To compile and run this, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ecdaa-119">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ecdaa-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ecdaa-120">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="ecdaa-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="ecdaa-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecdaa-121">See Also</span></span>  
 [<span data-ttu-id="ecdaa-122">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ecdaa-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
