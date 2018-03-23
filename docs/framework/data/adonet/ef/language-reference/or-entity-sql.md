---
title: '|| (OR) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b44934aa0db73f872f0ab27a4c36c5c615855de1
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2018
---
# <a name="-or-entity-sql"></a><span data-ttu-id="38623-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38623-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="38623-103">Verknüpft zwei `Boolean` -Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="38623-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38623-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38623-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="38623-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="38623-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="38623-106">Jeder gültige Ausdruck, der ein `Boolean`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="38623-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38623-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38623-107">Return Value</span></span>  
 <span data-ttu-id="38623-108">`true` , wenn eine der Bedingungen `true`ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="38623-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38623-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38623-109">Remarks</span></span>  
 <span data-ttu-id="38623-110">OR ist ein logischer Operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38623-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="38623-111">Er wird zur Verknüpfung zweier Bedingungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="38623-111">It is used to combine two conditions.</span></span> <span data-ttu-id="38623-112">Wenn in einer Anweisung mehrere logische Operatoren verwendet werden, werden OR-Operatoren nach AND-Operatoren ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="38623-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="38623-113">Sie können jedoch die Reihenfolge der Auswertung ändern, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="38623-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="38623-114">Zwei senkrechte Striche (&#124;&#124;) haben dieselbe Funktion wie der OR-Operator.</span><span class="sxs-lookup"><span data-stu-id="38623-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="38623-115">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="38623-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="38623-116">true</span><span class="sxs-lookup"><span data-stu-id="38623-116">TRUE</span></span>|<span data-ttu-id="38623-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="38623-117">TRUE</span></span>|<span data-ttu-id="38623-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="38623-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="38623-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="38623-119">TRUE</span></span>|<span data-ttu-id="38623-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="38623-120">FALSE</span></span>|<span data-ttu-id="38623-121">NULL</span><span class="sxs-lookup"><span data-stu-id="38623-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="38623-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="38623-122">TRUE</span></span>|<span data-ttu-id="38623-123">NULL</span><span class="sxs-lookup"><span data-stu-id="38623-123">NULL</span></span>|<span data-ttu-id="38623-124">NULL</span><span class="sxs-lookup"><span data-stu-id="38623-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="38623-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38623-125">Example</span></span>  
 <span data-ttu-id="38623-126">Die folgende Entity SQL-Abfrage verwendet den OR-Operator, um zwei `Boolean` -Ausdrücke zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="38623-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="38623-127">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="38623-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="38623-128">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="38623-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="38623-129">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="38623-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="38623-130">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="38623-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="38623-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38623-131">See Also</span></span>  
 [<span data-ttu-id="38623-132">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="38623-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
