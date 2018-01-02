---
title: (Modulo) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a04b2972c80aff654331aeb319390b6f817374bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="73c59-102">(Modulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="73c59-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="73c59-103">Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.</span><span class="sxs-lookup"><span data-stu-id="73c59-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73c59-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="73c59-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="73c59-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="73c59-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="73c59-106">The numeric expression to divide.</span></span> <span data-ttu-id="73c59-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="73c59-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="73c59-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="73c59-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="73c59-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="73c59-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="73c59-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="73c59-110">Result Types</span></span>  
 <span data-ttu-id="73c59-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="73c59-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c59-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73c59-112">Example</span></span>  
 <span data-ttu-id="73c59-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="73c59-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="73c59-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="73c59-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="73c59-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="73c59-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="73c59-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="73c59-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="73c59-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="73c59-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="73c59-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73c59-118">See Also</span></span>  
 [<span data-ttu-id="73c59-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="73c59-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
