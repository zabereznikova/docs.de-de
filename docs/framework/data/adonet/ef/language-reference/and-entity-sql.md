---
title: '&amp;&amp; (UND) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eab05f7454f8ebc88ed29030503bfa96d0c70756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605738"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="3f64a-102">&amp;&amp; (UND) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3f64a-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="3f64a-103">Gibt `true` zurück, wenn beide Ausdrücke `true`sind, andernfalls `false` oder `NULL`.</span><span class="sxs-lookup"><span data-stu-id="3f64a-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f64a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f64a-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f64a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3f64a-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="3f64a-106">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f64a-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f64a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f64a-107">Remarks</span></span>  
 <span data-ttu-id="3f64a-108">Zwei kaufmännische Und-Zeichen (&&) haben dieselbe Bedeutung wie der AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="3f64a-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="3f64a-109">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3f64a-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="3f64a-110">true</span><span class="sxs-lookup"><span data-stu-id="3f64a-110">TRUE</span></span>|<span data-ttu-id="3f64a-111">false</span><span class="sxs-lookup"><span data-stu-id="3f64a-111">FALSE</span></span>|<span data-ttu-id="3f64a-112">NULL</span><span class="sxs-lookup"><span data-stu-id="3f64a-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="3f64a-113">false</span><span class="sxs-lookup"><span data-stu-id="3f64a-113">FALSE</span></span>|<span data-ttu-id="3f64a-114">false</span><span class="sxs-lookup"><span data-stu-id="3f64a-114">FALSE</span></span>|<span data-ttu-id="3f64a-115">false</span><span class="sxs-lookup"><span data-stu-id="3f64a-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="3f64a-116">NULL</span><span class="sxs-lookup"><span data-stu-id="3f64a-116">NULL</span></span>|<span data-ttu-id="3f64a-117">false</span><span class="sxs-lookup"><span data-stu-id="3f64a-117">FALSE</span></span>|<span data-ttu-id="3f64a-118">NULL</span><span class="sxs-lookup"><span data-stu-id="3f64a-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f64a-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f64a-119">Example</span></span>  
 <span data-ttu-id="3f64a-120">In der folgenden Entity SQL-Abfrage wird die Verwendung des AND-Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3f64a-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="3f64a-121">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="3f64a-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3f64a-122">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3f64a-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3f64a-123">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3f64a-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3f64a-124">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="3f64a-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="3f64a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f64a-125">See also</span></span>

- [<span data-ttu-id="3f64a-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3f64a-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
