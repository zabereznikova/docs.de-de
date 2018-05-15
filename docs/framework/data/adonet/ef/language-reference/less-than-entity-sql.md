---
title: '&lt; (Kleiner als) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: e11f28fd05cb49524b5a0ff854f951385603602f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lt-less-than-entity-sql"></a><span data-ttu-id="ed723-102">&lt; (Kleiner als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ed723-102">&lt; (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="ed723-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="ed723-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed723-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed723-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed723-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ed723-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ed723-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ed723-106">Any valid expression.</span></span> <span data-ttu-id="ed723-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="ed723-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ed723-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="ed723-108">Result Types</span></span>  
 <span data-ttu-id="ed723-109">`true` , wenn der linke Ausdruck kleiner als der rechte Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ed723-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed723-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed723-110">Example</span></span>  
 <span data-ttu-id="ed723-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator < verwendet, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="ed723-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="ed723-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="ed723-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ed723-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ed723-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ed723-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ed723-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ed723-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="ed723-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="ed723-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed723-116">See Also</span></span>  
 [<span data-ttu-id="ed723-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ed723-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
