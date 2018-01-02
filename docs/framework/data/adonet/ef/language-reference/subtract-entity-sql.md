---
title: '- (Subtrahieren) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 20b9fd7dda34d3f6f19551d8f7e313196e0acc12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="58b47-102">- (Subtrahieren) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="58b47-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="58b47-103">Subtrahiert eine Zahl von einer anderen.</span><span class="sxs-lookup"><span data-stu-id="58b47-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58b47-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="58b47-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="58b47-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="58b47-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="58b47-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="58b47-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="58b47-107">Result Types</span></span>  
 <span data-ttu-id="58b47-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="58b47-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="58b47-109">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="58b47-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58b47-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58b47-110">Example</span></span>  
 <span data-ttu-id="58b47-111">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator „-“, um zwei Zahlen voneinander zu subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="58b47-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="58b47-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="58b47-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="58b47-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="58b47-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="58b47-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="58b47-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="58b47-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="58b47-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="58b47-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b47-116">See Also</span></span>  
 [<span data-ttu-id="58b47-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="58b47-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
