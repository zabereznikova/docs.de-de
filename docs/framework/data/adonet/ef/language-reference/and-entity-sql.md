---
title: '&amp;&amp;(Und) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eccad616de287a39c42e986cea84dc22feec7f70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150509"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="b4f89-102">&amp;&amp;(Und) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b4f89-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="b4f89-103">Gibt `true` zurück, wenn beide Ausdrücke `true`sind, andernfalls `false` oder `NULL`.</span><span class="sxs-lookup"><span data-stu-id="b4f89-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4f89-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="b4f89-105">oder</span><span class="sxs-lookup"><span data-stu-id="b4f89-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4f89-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="b4f89-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="b4f89-107">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b4f89-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f89-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4f89-108">Remarks</span></span>  
 <span data-ttu-id="b4f89-109">Zwei kaufmännische Und-Zeichen (&&) haben dieselbe Bedeutung wie der AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="b4f89-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="b4f89-110">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4f89-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="b4f89-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="b4f89-111">TRUE</span></span>|<span data-ttu-id="b4f89-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="b4f89-112">FALSE</span></span>|<span data-ttu-id="b4f89-113">NULL</span><span class="sxs-lookup"><span data-stu-id="b4f89-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="b4f89-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="b4f89-114">FALSE</span></span>|<span data-ttu-id="b4f89-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="b4f89-115">FALSE</span></span>|<span data-ttu-id="b4f89-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="b4f89-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="b4f89-117">NULL</span><span class="sxs-lookup"><span data-stu-id="b4f89-117">NULL</span></span>|<span data-ttu-id="b4f89-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="b4f89-118">FALSE</span></span>|<span data-ttu-id="b4f89-119">NULL</span><span class="sxs-lookup"><span data-stu-id="b4f89-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4f89-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4f89-120">Example</span></span>  
 <span data-ttu-id="b4f89-121">In der folgenden Entity SQL-Abfrage wird die Verwendung des AND-Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b4f89-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="b4f89-122">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b4f89-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b4f89-123">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b4f89-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b4f89-124">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b4f89-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b4f89-125">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b4f89-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="b4f89-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4f89-126">See also</span></span>

- [<span data-ttu-id="b4f89-127">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b4f89-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
