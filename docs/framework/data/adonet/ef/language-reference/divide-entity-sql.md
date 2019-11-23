---
title: '- Glie (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 79fdbebc648daac4f695387d52d2a915383f99ca
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833890"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="d5992-102">/ (Division) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d5992-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="d5992-103">Dividiert eine Zahl durch eine andere.</span><span class="sxs-lookup"><span data-stu-id="d5992-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5992-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5992-104">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5992-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d5992-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="d5992-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d5992-106">The numeric expression to divide.</span></span> <span data-ttu-id="d5992-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="d5992-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="d5992-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5992-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="d5992-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="d5992-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d5992-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="d5992-110">Result Types</span></span>  
 <span data-ttu-id="d5992-111">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="d5992-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d5992-112">Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="d5992-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5992-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5992-113">Example</span></span>  
 <span data-ttu-id="d5992-114">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator/, um eine Zahl durch eine andere zu dividieren.</span><span class="sxs-lookup"><span data-stu-id="d5992-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="d5992-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d5992-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d5992-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d5992-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d5992-117">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d5992-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d5992-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d5992-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="d5992-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5992-119">See also</span></span>

- [<span data-ttu-id="d5992-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d5992-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
