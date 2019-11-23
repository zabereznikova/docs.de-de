---
title: '>= (Größer als oder gleich) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 9e1d7e92097713ebdaf15523a5f99f98ed8be0b3
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833743"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="12a18-102">> = (größer als oder gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="12a18-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="12a18-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="12a18-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12a18-104">Syntax</span></span>  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="12a18-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="12a18-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="12a18-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="12a18-106">Any valid expression.</span></span> <span data-ttu-id="12a18-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="12a18-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="12a18-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="12a18-108">Result Types</span></span>  
 <span data-ttu-id="12a18-109">`true` , wenn der linke Ausdruck größer oder gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="12a18-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12a18-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12a18-110">Example</span></span>  
 <span data-ttu-id="12a18-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator >= verwendet, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="12a18-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="12a18-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="12a18-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="12a18-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="12a18-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="12a18-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="12a18-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="12a18-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="12a18-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="12a18-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12a18-116">See also</span></span>

- [<span data-ttu-id="12a18-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="12a18-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
