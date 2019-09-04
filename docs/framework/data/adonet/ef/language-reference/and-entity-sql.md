---
title: '&amp;&amp;Immer (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 02e404b73e5a9a9c3963e2d2b58ab7592afabc13
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251313"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="4aca6-102">&amp;&amp;Immer (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4aca6-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="4aca6-103">Gibt `true` zurück, wenn beide Ausdrücke `true`sind, andernfalls `false` oder `NULL`.</span><span class="sxs-lookup"><span data-stu-id="4aca6-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aca6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4aca6-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4aca6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4aca6-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="4aca6-106">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4aca6-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4aca6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4aca6-107">Remarks</span></span>  
 <span data-ttu-id="4aca6-108">Zwei kaufmännische Und-Zeichen (&&) haben dieselbe Bedeutung wie der AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="4aca6-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="4aca6-109">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4aca6-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="4aca6-110">true</span><span class="sxs-lookup"><span data-stu-id="4aca6-110">TRUE</span></span>|<span data-ttu-id="4aca6-111">false</span><span class="sxs-lookup"><span data-stu-id="4aca6-111">FALSE</span></span>|<span data-ttu-id="4aca6-112">NULL</span><span class="sxs-lookup"><span data-stu-id="4aca6-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="4aca6-113">false</span><span class="sxs-lookup"><span data-stu-id="4aca6-113">FALSE</span></span>|<span data-ttu-id="4aca6-114">false</span><span class="sxs-lookup"><span data-stu-id="4aca6-114">FALSE</span></span>|<span data-ttu-id="4aca6-115">false</span><span class="sxs-lookup"><span data-stu-id="4aca6-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="4aca6-116">NULL</span><span class="sxs-lookup"><span data-stu-id="4aca6-116">NULL</span></span>|<span data-ttu-id="4aca6-117">false</span><span class="sxs-lookup"><span data-stu-id="4aca6-117">FALSE</span></span>|<span data-ttu-id="4aca6-118">NULL</span><span class="sxs-lookup"><span data-stu-id="4aca6-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4aca6-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4aca6-119">Example</span></span>  
 <span data-ttu-id="4aca6-120">In der folgenden Entity SQL-Abfrage wird die Verwendung des AND-Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4aca6-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="4aca6-121">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="4aca6-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4aca6-122">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="4aca6-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4aca6-123">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4aca6-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4aca6-124">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="4aca6-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="4aca6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4aca6-125">See also</span></span>

- [<span data-ttu-id="4aca6-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="4aca6-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
