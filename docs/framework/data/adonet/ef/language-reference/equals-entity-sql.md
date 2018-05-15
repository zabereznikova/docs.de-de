---
title: = (Gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: bda314208a25426be321ba307be96067b1df2ac8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="80473-102">= (Gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80473-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="80473-103">Überprüft zwei Ausdrücke auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="80473-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80473-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80473-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="80473-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="80473-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="80473-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="80473-106">Any valid expression.</span></span> <span data-ttu-id="80473-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="80473-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="80473-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="80473-108">Result Types</span></span>  
 <span data-ttu-id="80473-109">`true` , wenn der linke Ausdruck gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="80473-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80473-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80473-110">Remarks</span></span>  
 <span data-ttu-id="80473-111">Der Operator "==" ist äquivalent zum Operator "=".</span><span class="sxs-lookup"><span data-stu-id="80473-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80473-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80473-112">Example</span></span>  
 <span data-ttu-id="80473-113">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="80473-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="80473-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="80473-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="80473-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="80473-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="80473-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="80473-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="80473-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="80473-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="80473-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80473-118">See Also</span></span>  
 [<span data-ttu-id="80473-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="80473-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
