---
title: = (Gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 5cdfd35450514a9699a39cf78f64c0fa6b7d5f39
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833851"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="1ef83-102">= (Gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1ef83-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="1ef83-103">Überprüft zwei Ausdrücke auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="1ef83-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ef83-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ef83-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1ef83-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1ef83-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1ef83-106">Any valid expression.</span></span> <span data-ttu-id="1ef83-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="1ef83-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1ef83-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="1ef83-108">Result Types</span></span>  
 <span data-ttu-id="1ef83-109">`true` , wenn der linke Ausdruck gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="1ef83-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ef83-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ef83-110">Remarks</span></span>  
 <span data-ttu-id="1ef83-111">Der Operator "==" ist äquivalent zum Operator "=".</span><span class="sxs-lookup"><span data-stu-id="1ef83-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef83-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef83-112">Example</span></span>  
 <span data-ttu-id="1ef83-113">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1ef83-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="1ef83-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="1ef83-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1ef83-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="1ef83-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1ef83-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1ef83-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1ef83-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="1ef83-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="1ef83-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ef83-118">See also</span></span>

- [<span data-ttu-id="1ef83-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="1ef83-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
