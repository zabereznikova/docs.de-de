---
title: '&amp;&amp;(UND) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e7255110a9118c3a31c84e3262fd5b1490d546e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="9cd68-102">&amp;&amp;(UND) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9cd68-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="9cd68-103">Gibt `true` zurück, wenn beide Ausdrücke `true`sind, andernfalls `false` oder `NULL`.</span><span class="sxs-lookup"><span data-stu-id="9cd68-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cd68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cd68-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9cd68-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9cd68-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="9cd68-106">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9cd68-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cd68-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cd68-107">Remarks</span></span>  
 <span data-ttu-id="9cd68-108">Zwei kaufmännische Und-Zeichen (&&) haben dieselbe Bedeutung wie der AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="9cd68-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="9cd68-109">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9cd68-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="9cd68-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="9cd68-110">TRUE</span></span>|<span data-ttu-id="9cd68-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="9cd68-111">FALSE</span></span>|<span data-ttu-id="9cd68-112">NULL</span><span class="sxs-lookup"><span data-stu-id="9cd68-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="9cd68-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="9cd68-113">FALSE</span></span>|<span data-ttu-id="9cd68-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="9cd68-114">FALSE</span></span>|<span data-ttu-id="9cd68-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="9cd68-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="9cd68-116">NULL</span><span class="sxs-lookup"><span data-stu-id="9cd68-116">NULL</span></span>|<span data-ttu-id="9cd68-117">false</span><span class="sxs-lookup"><span data-stu-id="9cd68-117">FALSE</span></span>|<span data-ttu-id="9cd68-118">NULL</span><span class="sxs-lookup"><span data-stu-id="9cd68-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9cd68-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cd68-119">Example</span></span>  
 <span data-ttu-id="9cd68-120">In der folgenden Entity SQL-Abfrage wird die Verwendung des AND-Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9cd68-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="9cd68-121">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="9cd68-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9cd68-122">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="9cd68-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9cd68-123">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9cd68-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9cd68-124">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="9cd68-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="9cd68-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cd68-125">See Also</span></span>  
 [<span data-ttu-id="9cd68-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9cd68-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
