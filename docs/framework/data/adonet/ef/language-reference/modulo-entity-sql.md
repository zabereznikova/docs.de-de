---
title: (Modulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: ad7b76c1479906e9dcd875407e75475b55d5ae16
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764540"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="378e6-102">(Modulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="378e6-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="378e6-103">Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.</span><span class="sxs-lookup"><span data-stu-id="378e6-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="378e6-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="378e6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="378e6-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="378e6-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="378e6-106">The numeric expression to divide.</span></span> <span data-ttu-id="378e6-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="378e6-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="378e6-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="378e6-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="378e6-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="378e6-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="378e6-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="378e6-110">Result Types</span></span>  
 <span data-ttu-id="378e6-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="378e6-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="378e6-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="378e6-112">Example</span></span>  
 <span data-ttu-id="378e6-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="378e6-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="378e6-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="378e6-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="378e6-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="378e6-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="378e6-116">Verwenden Sie das Verfahren unter [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)</span><span class="sxs-lookup"><span data-stu-id="378e6-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="378e6-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="378e6-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="378e6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="378e6-118">See Also</span></span>  
 [<span data-ttu-id="378e6-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="378e6-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
