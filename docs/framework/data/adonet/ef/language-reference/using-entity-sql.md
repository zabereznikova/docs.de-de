---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034093"
---
# <a name="using-entity-sql"></a><span data-ttu-id="8b549-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8b549-102">USING (Entity SQL)</span></span>
<span data-ttu-id="8b549-103">Legt in einem Abfrageausdruck verwendete Namespaces fest.</span><span class="sxs-lookup"><span data-stu-id="8b549-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b549-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b549-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b549-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8b549-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="8b549-106">Legt einen kürzeren Alias für die Qualifizierung eines Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="8b549-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="8b549-107">Jeder gültige Namespace.</span><span class="sxs-lookup"><span data-stu-id="8b549-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b549-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b549-108">Example</span></span>  
 <span data-ttu-id="8b549-109">Die folgende Entity SQL-Abfrage legt mithilfe des USING-Operators Namespaces fest, die in einem Abfrageausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b549-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="8b549-110">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="8b549-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8b549-111">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b549-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="8b549-112">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="8b549-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b549-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b549-113">See also</span></span>

- [<span data-ttu-id="8b549-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="8b549-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="8b549-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="8b549-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
