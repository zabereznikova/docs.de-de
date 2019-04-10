---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 4e2a387cf400a881dfd91c61b36ee3ce0f5a4431
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309432"
---
# <a name="set-entity-sql"></a><span data-ttu-id="5eb84-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5eb84-102">SET (Entity SQL)</span></span>
<span data-ttu-id="5eb84-103">Der SET-Ausdruck wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="5eb84-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5eb84-104">Syntax</span></span>  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5eb84-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5eb84-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5eb84-106">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5eb84-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5eb84-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5eb84-107">Remarks</span></span>  
 <span data-ttu-id="5eb84-108">Der Mengenausdruck `SET(c)` ist logisch äquivalent zur folgenden SELECTAnweisung:</span><span class="sxs-lookup"><span data-stu-id="5eb84-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` <span data-ttu-id="5eb84-109">zählt die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5eb84-109">is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5eb84-110">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5eb84-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5eb84-111">Finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5eb84-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb84-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5eb84-112">Example</span></span>  
 <span data-ttu-id="5eb84-113">Die folgende Entity SQL-Abfrage verwendet den SET-Ausdruck, um eine Auflistung von Objekten in eine Menge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="5eb84-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="5eb84-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5eb84-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5eb84-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5eb84-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5eb84-116">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5eb84-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="5eb84-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5eb84-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a><span data-ttu-id="5eb84-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eb84-118">See also</span></span>

- [<span data-ttu-id="5eb84-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5eb84-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
