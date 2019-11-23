---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833838"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="6f612-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6f612-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="6f612-103">Bestimmt, ob eine Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="6f612-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f612-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f612-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f612-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6f612-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6f612-106">Jeder gültige Ausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6f612-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="6f612-107">NOT</span><span class="sxs-lookup"><span data-stu-id="6f612-107">NOT</span></span>  
 <span data-ttu-id="6f612-108">Gibt an, dass das Ergebnis von EXISTS negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f612-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f612-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f612-109">Return Value</span></span>  
 <span data-ttu-id="6f612-110">`true`, wenn die Auflistung nicht leer ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6f612-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f612-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f612-111">Remarks</span></span>  
 <span data-ttu-id="6f612-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]EXISTS{2} ist einer der {3}-Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="6f612-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="6f612-113">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6f612-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="6f612-114">Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengen Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="6f612-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f612-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f612-115">Example</span></span>  
 <span data-ttu-id="6f612-116">Die folgende Entity SQL-Abfrage verwendet den EXISTS-Operator, um festzustellen, ob die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="6f612-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="6f612-117">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="6f612-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6f612-118">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="6f612-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6f612-119">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6f612-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6f612-120">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="6f612-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="6f612-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f612-121">See also</span></span>

- [<span data-ttu-id="6f612-122">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6f612-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
