---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 72d96c5f24fcedf870370de3792680831145a454
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311135"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="55bf9-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="55bf9-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="55bf9-103">Bestimmt, ob eine Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="55bf9-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55bf9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55bf9-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="55bf9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="55bf9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="55bf9-106">Jeder gültige Ausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="55bf9-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="55bf9-107">NICHT</span><span class="sxs-lookup"><span data-stu-id="55bf9-107">NOT</span></span>  
 <span data-ttu-id="55bf9-108">Gibt an, dass das Ergebnis von EXISTS negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="55bf9-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55bf9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="55bf9-109">Return Value</span></span>  
 <span data-ttu-id="55bf9-110">`true`, wenn die Auflistung nicht leer ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="55bf9-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55bf9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55bf9-111">Remarks</span></span>  
 <span data-ttu-id="55bf9-112">EXISTS[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist einer der -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="55bf9-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="55bf9-113">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="55bf9-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="55bf9-114">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren, finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="55bf9-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55bf9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55bf9-115">Example</span></span>  
 <span data-ttu-id="55bf9-116">Die folgende Entity SQL-Abfrage verwendet den EXISTS-Operator, um festzustellen, ob die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="55bf9-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="55bf9-117">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="55bf9-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="55bf9-118">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="55bf9-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="55bf9-119">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="55bf9-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="55bf9-120">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="55bf9-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="55bf9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55bf9-121">See also</span></span>

- [<span data-ttu-id="55bf9-122">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="55bf9-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
