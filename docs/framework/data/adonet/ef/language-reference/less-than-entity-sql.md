---
title: '&lt; (Kleiner als) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 14e1af042601c11cae32dd3046dee73ec4fd209f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lt-less-than-entity-sql"></a><span data-ttu-id="3bf5b-102">&lt; (Kleiner als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3bf5b-102">&lt; (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="3bf5b-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bf5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bf5b-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3bf5b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3bf5b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3bf5b-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-106">Any valid expression.</span></span> <span data-ttu-id="3bf5b-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3bf5b-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="3bf5b-108">Result Types</span></span>  
 <span data-ttu-id="3bf5b-109">`true` , wenn der linke Ausdruck kleiner als der rechte Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf5b-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bf5b-110">Example</span></span>  
 <span data-ttu-id="3bf5b-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator < verwendet, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="3bf5b-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="3bf5b-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3bf5b-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3bf5b-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3bf5b-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3bf5b-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="3bf5b-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="3bf5b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bf5b-116">See Also</span></span>  
 [<span data-ttu-id="3bf5b-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3bf5b-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
