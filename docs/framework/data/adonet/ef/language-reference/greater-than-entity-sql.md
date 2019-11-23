---
title: '> (Größer als) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: f2d3a0ed81cf75b7e567dbd07e119629ea47ac69
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833773"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="b716f-102">> (Größer als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b716f-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="b716f-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="b716f-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b716f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b716f-104">Syntax</span></span>  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b716f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b716f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b716f-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b716f-106">Any valid expression.</span></span> <span data-ttu-id="b716f-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="b716f-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b716f-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="b716f-108">Result Types</span></span>  
 <span data-ttu-id="b716f-109">`true` , wenn der linke Ausdruck größer als der rechte Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b716f-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b716f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b716f-110">Example</span></span>  
 <span data-ttu-id="b716f-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator > verwendet, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="b716f-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="b716f-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b716f-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b716f-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b716f-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b716f-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b716f-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b716f-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b716f-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="b716f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b716f-116">See also</span></span>

- [<span data-ttu-id="b716f-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b716f-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
