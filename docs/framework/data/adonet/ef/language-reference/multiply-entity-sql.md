---
title: '* (Multiplizieren) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: ecb0a55e403dddc5f7e69947035c8aa1fe7560ad
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762545"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="024ed-102">\* (Multiplikation) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="024ed-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="024ed-103">Multipliziert zwei Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="024ed-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="024ed-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="024ed-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="024ed-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="024ed-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="024ed-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="024ed-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="024ed-107">Result Types</span></span>  
 <span data-ttu-id="024ed-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="024ed-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="024ed-109">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="024ed-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="024ed-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="024ed-110">Example</span></span>  
 <span data-ttu-id="024ed-111">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "\*", um zwei Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="024ed-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="024ed-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="024ed-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="024ed-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="024ed-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="024ed-114">Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)</span><span class="sxs-lookup"><span data-stu-id="024ed-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="024ed-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="024ed-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="024ed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="024ed-116">See Also</span></span>  
 [<span data-ttu-id="024ed-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="024ed-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
