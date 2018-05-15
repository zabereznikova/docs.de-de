---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 17bc89e6e97b037db035a6f65cd0ec82b840c308
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="-not-entity-sql"></a><span data-ttu-id="4c0d7-103">!</span><span class="sxs-lookup"><span data-stu-id="4c0d7-103">!</span></span> <span data-ttu-id="4c0d7-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4c0d7-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="4c0d7-105">Negiert einen `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c0d7-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0d7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c0d7-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c0d7-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="4c0d7-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="4c0d7-108">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c0d7-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c0d7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c0d7-109">Remarks</span></span>  
 <span data-ttu-id="4c0d7-110">Das Ausrufezeichen (!) hat dieselbe Bedeutung wie der NOT-Operator.</span><span class="sxs-lookup"><span data-stu-id="4c0d7-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0d7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c0d7-111">Example</span></span>  
 <span data-ttu-id="4c0d7-112">Die folgende Entity SQL-Abfrage verwendet den NOT-Operator, um einen `Boolean` -Ausdruck zu negieren.</span><span class="sxs-lookup"><span data-stu-id="4c0d7-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="4c0d7-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="4c0d7-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4c0d7-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="4c0d7-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4c0d7-115">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4c0d7-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4c0d7-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="4c0d7-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="4c0d7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c0d7-117">See Also</span></span>  
 [<span data-ttu-id="4c0d7-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="4c0d7-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
