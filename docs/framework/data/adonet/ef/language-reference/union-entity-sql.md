---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 9c4106d26fb73219d7b5f0c6763736aaf9163d4b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200978"
---
# <a name="union-entity-sql"></a><span data-ttu-id="01c42-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="01c42-102">UNION (Entity SQL)</span></span>

<span data-ttu-id="01c42-103">Fasst die Ergebnisse von zwei oder mehr Abfragen in einer Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="01c42-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01c42-104">Syntax</span></span>  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="01c42-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="01c42-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="01c42-106">Jeder gültige Abfrageausdruck, der eine mit der Auflistung zusammenzufassende Auflistung zurückgibt. Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`sein.</span><span class="sxs-lookup"><span data-stu-id="01c42-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="01c42-107">UNION</span><span class="sxs-lookup"><span data-stu-id="01c42-107">UNION</span></span>  
 <span data-ttu-id="01c42-108">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="01c42-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="01c42-109">ALL</span><span class="sxs-lookup"><span data-stu-id="01c42-109">ALL</span></span>  
 <span data-ttu-id="01c42-110">Gibt an, dass mehrere Auflistungen kombiniert und als einzelne Auflistung zurückgegeben werden sollen, wobei Duplikate erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="01c42-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="01c42-111">Wenn dies nicht angegeben wird, werden Duplikate aus der Ergebnisauflistung entfernt.</span><span class="sxs-lookup"><span data-stu-id="01c42-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01c42-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01c42-112">Return Value</span></span>  

 <span data-ttu-id="01c42-113">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="01c42-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01c42-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01c42-114">Remarks</span></span>  

 <span data-ttu-id="01c42-115">UNION ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="01c42-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="01c42-116">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="01c42-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="01c42-117">Informationen zur Rangfolge der-Mengen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="01c42-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01c42-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01c42-118">Example</span></span>  

 <span data-ttu-id="01c42-119">Die folgende Entity SQL-Abfrage verwendet den UNION ALL-Operator, um die Ergebnisse von zwei Abfragen in einer Auflistung zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="01c42-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="01c42-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="01c42-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="01c42-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="01c42-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="01c42-122">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="01c42-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="01c42-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="01c42-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a><span data-ttu-id="01c42-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01c42-124">See also</span></span>

- [<span data-ttu-id="01c42-125">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="01c42-125">Entity SQL Reference</span></span>](entity-sql-reference.md)
