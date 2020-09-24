---
title: = (Gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148086"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="29cbf-102">= (Gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="29cbf-102">= (Equals) (Entity SQL)</span></span>

<span data-ttu-id="29cbf-103">Überprüft zwei Ausdrücke auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="29cbf-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29cbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29cbf-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="29cbf-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="29cbf-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="29cbf-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="29cbf-106">Any valid expression.</span></span> <span data-ttu-id="29cbf-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen.</span><span class="sxs-lookup"><span data-stu-id="29cbf-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="29cbf-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="29cbf-108">Result Types</span></span>  

 <span data-ttu-id="29cbf-109">`true` , wenn der linke Ausdruck gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="29cbf-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29cbf-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="29cbf-110">Remarks</span></span>  

 <span data-ttu-id="29cbf-111">Der Operator "==" ist äquivalent zum Operator "=".</span><span class="sxs-lookup"><span data-stu-id="29cbf-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29cbf-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29cbf-112">Example</span></span>  

 <span data-ttu-id="29cbf-113">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="29cbf-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="29cbf-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="29cbf-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="29cbf-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="29cbf-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="29cbf-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="29cbf-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="29cbf-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="29cbf-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="29cbf-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29cbf-118">See also</span></span>

- [<span data-ttu-id="29cbf-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="29cbf-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
