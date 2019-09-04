---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 20e18bf536f2b89eca9515b3c5dca7ca7fbd6fe5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250992"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="ce924-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ce924-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="ce924-103">Bestimmt, ob eine Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="ce924-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce924-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce924-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce924-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ce924-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ce924-106">Jeder gültige Ausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ce924-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="ce924-107">NICHT</span><span class="sxs-lookup"><span data-stu-id="ce924-107">NOT</span></span>  
 <span data-ttu-id="ce924-108">Gibt an, dass das Ergebnis von EXISTS negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce924-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce924-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce924-109">Return Value</span></span>  
 <span data-ttu-id="ce924-110">`true`, wenn die Auflistung nicht leer ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="ce924-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce924-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce924-111">Remarks</span></span>  
 <span data-ttu-id="ce924-112">EXISTS[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist einer der -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="ce924-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ce924-113">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ce924-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ce924-114">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="ce924-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce924-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce924-115">Example</span></span>  
 <span data-ttu-id="ce924-116">Die folgende Entity SQL-Abfrage verwendet den EXISTS-Operator, um festzustellen, ob die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="ce924-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="ce924-117">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="ce924-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ce924-118">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ce924-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ce924-119">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ce924-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ce924-120">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="ce924-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="ce924-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce924-121">See also</span></span>

- [<span data-ttu-id="ce924-122">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ce924-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
