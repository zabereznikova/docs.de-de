---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319357"
---
# <a name="set-entity-sql"></a><span data-ttu-id="b6d2d-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b6d2d-102">SET (Entity SQL)</span></span>
<span data-ttu-id="b6d2d-103">Der SET-Ausdruck wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6d2d-104">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6d2d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b6d2d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b6d2d-106">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6d2d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6d2d-107">Remarks</span></span>  
 <span data-ttu-id="b6d2d-108">Der Mengenausdruck `SET(c)` ist logisch äquivalent zur folgenden SELECTAnweisung:</span><span class="sxs-lookup"><span data-stu-id="b6d2d-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="b6d2d-109">`SET` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="b6d2d-110">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="b6d2d-111">Weitere [Informationen](except-entity-sql.md) zu den [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Mengen Operatoren finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6d2d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6d2d-112">Example</span></span>  
 <span data-ttu-id="b6d2d-113">Die folgende Entity SQL-Abfrage verwendet den SET-Ausdruck, um eine Auflistung von Objekten in eine Menge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="b6d2d-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b6d2d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b6d2d-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b6d2d-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b6d2d-116">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b6d2d-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="b6d2d-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b6d2d-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="b6d2d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6d2d-118">See also</span></span>

- [<span data-ttu-id="b6d2d-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b6d2d-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
