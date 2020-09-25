---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 6902a44af343c37ccb26412738d9f96b28551814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204423"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="3ae42-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3ae42-102">OVERLAPS (Entity SQL)</span></span>

<span data-ttu-id="3ae42-103">Bestimmt, ob zwei Auflistungen über gemeinsame Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="3ae42-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ae42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ae42-104">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ae42-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3ae42-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="3ae42-106">Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3ae42-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="3ae42-107">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="3ae42-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ae42-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ae42-108">Return Value</span></span>  

 <span data-ttu-id="3ae42-109">`true` , wenn die beiden Auflistungen gemeinsame Elemente aufweisen, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="3ae42-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ae42-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3ae42-110">Remarks</span></span>  

 <span data-ttu-id="3ae42-111">Überlappungen bieten funktionale Entsprechungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3ae42-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="3ae42-112">OVERLAPS ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="3ae42-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="3ae42-113">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="3ae42-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="3ae42-114">Informationen zur Rangfolge der-Mengen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatoren finden Sie unter [Ausnahme](except-entity-sql.md)von.</span><span class="sxs-lookup"><span data-stu-id="3ae42-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae42-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ae42-115">Example</span></span>  

 <span data-ttu-id="3ae42-116">Die folgende Entity SQL-Abfrage verwendet den OVERLAPS-Operator, um zu bestimmen, ob zwei Auflistungen einen gemeinsamen Wert haben.</span><span class="sxs-lookup"><span data-stu-id="3ae42-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="3ae42-117">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="3ae42-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3ae42-118">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3ae42-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="3ae42-119">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3ae42-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3ae42-120">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="3ae42-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="3ae42-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ae42-121">See also</span></span>

- [<span data-ttu-id="3ae42-122">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3ae42-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
