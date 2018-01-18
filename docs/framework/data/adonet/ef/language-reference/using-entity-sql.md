---
title: USING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d1a47102c7057918c981b53f920afef09b20afad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="using-entity-sql"></a><span data-ttu-id="c168a-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c168a-102">USING (Entity SQL)</span></span>
<span data-ttu-id="c168a-103">Legt in einem Abfrageausdruck verwendete Namespaces fest.</span><span class="sxs-lookup"><span data-stu-id="c168a-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c168a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c168a-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="c168a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c168a-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="c168a-106">Legt einen kürzeren Alias für die Qualifizierung eines Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="c168a-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="c168a-107">Jeder gültige Namespace.</span><span class="sxs-lookup"><span data-stu-id="c168a-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c168a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c168a-108">Example</span></span>  
 <span data-ttu-id="c168a-109">Die folgende Entity SQL-Abfrage legt mithilfe des USING-Operators Namespaces fest, die in einem Abfrageausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c168a-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="c168a-110">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c168a-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c168a-111">Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c168a-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="c168a-112">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="c168a-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="c168a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c168a-113">See Also</span></span>  
 [<span data-ttu-id="c168a-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c168a-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [<span data-ttu-id="c168a-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="c168a-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
