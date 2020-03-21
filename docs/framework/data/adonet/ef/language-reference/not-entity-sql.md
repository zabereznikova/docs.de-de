---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0b69d4cb64adc1f9232631d50ec42af0d1ba47e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150128"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="07b9f-103">!</span><span class="sxs-lookup"><span data-stu-id="07b9f-103">!</span></span> <span data-ttu-id="07b9f-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="07b9f-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="07b9f-105">Negiert einen `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="07b9f-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07b9f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="07b9f-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="07b9f-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="07b9f-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="07b9f-108">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="07b9f-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07b9f-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07b9f-109">Remarks</span></span>  
 <span data-ttu-id="07b9f-110">Das Ausrufezeichen (!) hat dieselbe Bedeutung wie der NOT-Operator.</span><span class="sxs-lookup"><span data-stu-id="07b9f-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07b9f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07b9f-111">Example</span></span>  
 <span data-ttu-id="07b9f-112">Die folgende Entity SQL-Abfrage verwendet den NOT-Operator, um einen `Boolean` -Ausdruck zu negieren.</span><span class="sxs-lookup"><span data-stu-id="07b9f-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="07b9f-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="07b9f-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="07b9f-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="07b9f-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="07b9f-115">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="07b9f-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="07b9f-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="07b9f-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="07b9f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07b9f-117">See also</span></span>

- [<span data-ttu-id="07b9f-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="07b9f-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
