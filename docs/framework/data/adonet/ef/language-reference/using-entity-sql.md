---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203591"
---
# <a name="using-entity-sql"></a><span data-ttu-id="b52e9-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b52e9-102">USING (Entity SQL)</span></span>

<span data-ttu-id="b52e9-103">Legt in einem Abfrageausdruck verwendete Namespaces fest.</span><span class="sxs-lookup"><span data-stu-id="b52e9-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b52e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b52e9-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="b52e9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b52e9-105">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="b52e9-106">Legt einen kürzeren Alias für die Qualifizierung eines Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="b52e9-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="b52e9-107">Jeder gültige Namespace.</span><span class="sxs-lookup"><span data-stu-id="b52e9-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b52e9-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b52e9-108">Example</span></span>  

 <span data-ttu-id="b52e9-109">Die folgende Entity SQL-Abfrage legt mithilfe des USING-Operators Namespaces fest, die in einem Abfrageausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b52e9-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="b52e9-110">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b52e9-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b52e9-111">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b52e9-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="b52e9-112">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b52e9-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b52e9-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b52e9-113">See also</span></span>

- [<span data-ttu-id="b52e9-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="b52e9-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="b52e9-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b52e9-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
