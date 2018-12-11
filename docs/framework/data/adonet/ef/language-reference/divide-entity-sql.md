---
title: '- (Division) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 38feaf4509ea2ed2838efe4daa257cdff144e863
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147696"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="18e14-102">/ (Division) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="18e14-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="18e14-103">Dividiert eine Zahl durch eine andere.</span><span class="sxs-lookup"><span data-stu-id="18e14-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18e14-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="18e14-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="18e14-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="18e14-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="18e14-106">The numeric expression to divide.</span></span> <span data-ttu-id="18e14-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="18e14-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="18e14-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="18e14-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="18e14-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="18e14-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="18e14-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="18e14-110">Result Types</span></span>  
 <span data-ttu-id="18e14-111">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="18e14-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="18e14-112">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="18e14-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18e14-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18e14-113">Example</span></span>  
 <span data-ttu-id="18e14-114">Die folgende Entity SQL-Abfrage verwendet die / arithmetischer Operator, um eine Zahl durch einen anderen zu teilen.</span><span class="sxs-lookup"><span data-stu-id="18e14-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="18e14-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="18e14-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="18e14-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="18e14-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="18e14-117">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="18e14-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="18e14-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="18e14-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="18e14-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18e14-119">See Also</span></span>  
 [<span data-ttu-id="18e14-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="18e14-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
