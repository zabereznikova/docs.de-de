---
title: '- (Subtrahieren) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 2e4c08788ea57000e189c8371f0494641931184b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797656"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="0e717-102">- (Subtrahieren) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0e717-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="0e717-103">Subtrahiert eine Zahl von einer anderen.</span><span class="sxs-lookup"><span data-stu-id="0e717-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e717-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e717-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e717-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0e717-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0e717-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="0e717-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0e717-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="0e717-107">Result Types</span></span>  
 <span data-ttu-id="0e717-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="0e717-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="0e717-109">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0e717-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e717-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e717-110">Example</span></span>  
 <span data-ttu-id="0e717-111">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator „-“, um zwei Zahlen voneinander zu subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="0e717-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="0e717-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="0e717-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0e717-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="0e717-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0e717-114">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0e717-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0e717-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="0e717-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="0e717-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e717-116">See also</span></span>

- [<span data-ttu-id="0e717-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="0e717-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
