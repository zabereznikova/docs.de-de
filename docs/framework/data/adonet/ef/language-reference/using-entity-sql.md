---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 6a5b374bc253cb2deb7a9e1de942c32d8e8bbfcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168024"
---
# <a name="using-entity-sql"></a><span data-ttu-id="8960d-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8960d-102">USING (Entity SQL)</span></span>
<span data-ttu-id="8960d-103">Legt in einem Abfrageausdruck verwendete Namespaces fest.</span><span class="sxs-lookup"><span data-stu-id="8960d-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8960d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8960d-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="8960d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8960d-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="8960d-106">Legt einen kürzeren Alias für die Qualifizierung eines Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="8960d-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="8960d-107">Jeder gültige Namespace.</span><span class="sxs-lookup"><span data-stu-id="8960d-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8960d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8960d-108">Example</span></span>  
 <span data-ttu-id="8960d-109">Die folgende Entity SQL-Abfrage legt mithilfe des USING-Operators Namespaces fest, die in einem Abfrageausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8960d-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="8960d-110">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="8960d-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8960d-111">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8960d-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="8960d-112">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="8960d-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="8960d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8960d-113">See also</span></span>

- [<span data-ttu-id="8960d-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="8960d-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="8960d-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="8960d-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
