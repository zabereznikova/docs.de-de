---
title: < (Kleiner als) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: fb3f4a1c6bc0df6af3c27836f7b53b2701776366
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319691"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="2654e-102">\< (Kleiner als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2654e-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="2654e-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="2654e-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2654e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2654e-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2654e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2654e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2654e-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2654e-106">Any valid expression.</span></span> <span data-ttu-id="2654e-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="2654e-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2654e-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="2654e-108">Result Types</span></span>  
 <span data-ttu-id="2654e-109">`true` , wenn der linke Ausdruck kleiner als der rechte Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2654e-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2654e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2654e-110">Example</span></span>  
 <span data-ttu-id="2654e-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator < verwendet, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="2654e-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="2654e-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="2654e-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2654e-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2654e-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2654e-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2654e-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2654e-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="2654e-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="2654e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2654e-116">See also</span></span>

- [<span data-ttu-id="2654e-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="2654e-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
