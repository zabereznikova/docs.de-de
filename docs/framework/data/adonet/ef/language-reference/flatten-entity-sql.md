---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 75463ed622ac969eb2690c4118861823479a2caa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="cc70e-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cc70e-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="cc70e-103">Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="cc70e-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="cc70e-104">Die neue Auflistung enthält dieselben Elemente wie die alte Auflistung, jedoch ohne geschachtelte Struktur.</span><span class="sxs-lookup"><span data-stu-id="cc70e-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc70e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc70e-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc70e-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="cc70e-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="cc70e-107">Jeder gültige Ausdruck, der eine zu einer einzigen Auflistung zu vereinfachende Auflistung von Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cc70e-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc70e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc70e-108">Remarks</span></span>  
 <span data-ttu-id="cc70e-109">`FLATTEN` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="cc70e-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="cc70e-110">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cc70e-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="cc70e-111">Finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="cc70e-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc70e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc70e-112">Example</span></span>  
 <span data-ttu-id="cc70e-113">Die folgende Entity SQL-Abfrage verwendet den `FLATTEN` -Operator, um eine Auflistung von Auflistungen in eine vereinfachte Auflistung zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="cc70e-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="cc70e-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cc70e-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cc70e-115">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cc70e-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cc70e-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="cc70e-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="cc70e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc70e-117">See Also</span></span>  
 [<span data-ttu-id="cc70e-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="cc70e-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
