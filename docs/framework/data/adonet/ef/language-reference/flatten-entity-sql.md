---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 327a20bbc53566846e7d828f511bcd1d25cc5504
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250966"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="90de3-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="90de3-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="90de3-103">Konvertiert eine Auflistung von Auflistungen in eine vereinfachte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="90de3-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="90de3-104">Die neue Auflistung enthält dieselben Elemente wie die alte Auflistung, jedoch ohne geschachtelte Struktur.</span><span class="sxs-lookup"><span data-stu-id="90de3-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90de3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="90de3-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="90de3-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="90de3-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="90de3-107">Jeder gültige Ausdruck, der eine zu einer einzigen Auflistung zu vereinfachende Auflistung von Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="90de3-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90de3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90de3-108">Remarks</span></span>  
 <span data-ttu-id="90de3-109">`FLATTEN` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="90de3-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="90de3-110">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90de3-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="90de3-111">Siehe [mit Ausnahme](except-entity-sql.md) der Rang folgen Informationen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] für die Mengen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="90de3-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90de3-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90de3-112">Example</span></span>  
 <span data-ttu-id="90de3-113">Die folgende Entity SQL-Abfrage verwendet den `FLATTEN` -Operator, um eine Auflistung von Auflistungen in eine vereinfachte Auflistung zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="90de3-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="90de3-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="90de3-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="90de3-115">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="90de3-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="90de3-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="90de3-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="90de3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90de3-117">See also</span></span>

- [<span data-ttu-id="90de3-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="90de3-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
