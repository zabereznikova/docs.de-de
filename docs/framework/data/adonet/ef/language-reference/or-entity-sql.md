---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 89c0a92030f2f067d5e5d45b58d475414a224ce4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150803"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="5ab9b-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5ab9b-102">|| (OR) (Entity SQL)</span></span>

<span data-ttu-id="5ab9b-103">Verknüpft zwei `Boolean` -Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ab9b-104">Syntax</span></span>  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ab9b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5ab9b-105">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="5ab9b-106">Jeder gültige Ausdruck, der ein `Boolean`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ab9b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ab9b-107">Return Value</span></span>  

 <span data-ttu-id="5ab9b-108">`true` , wenn eine der Bedingungen `true`ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ab9b-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5ab9b-109">Remarks</span></span>  

 <span data-ttu-id="5ab9b-110">OR ist ein logischer Operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ab9b-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="5ab9b-111">Er wird zur Verknüpfung zweier Bedingungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-111">It is used to combine two conditions.</span></span> <span data-ttu-id="5ab9b-112">Werden in einem Ausdruck mehrere logische Operatoren verwendet, werden OR-Operatoren nach AND-Operatoren ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="5ab9b-113">Sie können jedoch die Reihenfolge der Auswertung ändern, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="5ab9b-114">Doppelte vertikale Balken (&#124;&#124;) haben dieselbe Funktion wie der or-Operator.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="5ab9b-115">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="5ab9b-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-116">TRUE</span></span>|<span data-ttu-id="5ab9b-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-117">TRUE</span></span>|<span data-ttu-id="5ab9b-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="5ab9b-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-119">TRUE</span></span>|<span data-ttu-id="5ab9b-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-120">FALSE</span></span>|<span data-ttu-id="5ab9b-121">NULL</span><span class="sxs-lookup"><span data-stu-id="5ab9b-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="5ab9b-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="5ab9b-122">TRUE</span></span>|<span data-ttu-id="5ab9b-123">NULL</span><span class="sxs-lookup"><span data-stu-id="5ab9b-123">NULL</span></span>|<span data-ttu-id="5ab9b-124">NULL</span><span class="sxs-lookup"><span data-stu-id="5ab9b-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5ab9b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ab9b-125">Example</span></span>  

 <span data-ttu-id="5ab9b-126">Die folgende Entity SQL-Abfrage verwendet den OR-Operator, um zwei `Boolean` -Ausdrücke zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="5ab9b-127">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5ab9b-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5ab9b-128">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5ab9b-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5ab9b-129">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5ab9b-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5ab9b-130">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5ab9b-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a><span data-ttu-id="5ab9b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ab9b-131">See also</span></span>

- [<span data-ttu-id="5ab9b-132">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5ab9b-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
