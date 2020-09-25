---
title: '&amp;&amp; Immer (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198040"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="32d56-102">&amp;&amp; Immer (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="32d56-102">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="32d56-103">Gibt `true` zurück, wenn beide Ausdrücke `true`sind, andernfalls `false` oder `NULL`.</span><span class="sxs-lookup"><span data-stu-id="32d56-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32d56-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="32d56-105">oder</span><span class="sxs-lookup"><span data-stu-id="32d56-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="32d56-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="32d56-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="32d56-107">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="32d56-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32d56-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32d56-108">Remarks</span></span>  

 <span data-ttu-id="32d56-109">Zwei kaufmännische Und-Zeichen (&&) haben dieselbe Bedeutung wie der AND-Operator.</span><span class="sxs-lookup"><span data-stu-id="32d56-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="32d56-110">In der folgenden Tabelle werden mögliche Eingabewerte und Rückgabetypen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="32d56-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="32d56-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="32d56-111">TRUE</span></span>|<span data-ttu-id="32d56-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="32d56-112">FALSE</span></span>|<span data-ttu-id="32d56-113">NULL</span><span class="sxs-lookup"><span data-stu-id="32d56-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="32d56-114">false</span><span class="sxs-lookup"><span data-stu-id="32d56-114">FALSE</span></span>|<span data-ttu-id="32d56-115">false</span><span class="sxs-lookup"><span data-stu-id="32d56-115">FALSE</span></span>|<span data-ttu-id="32d56-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="32d56-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="32d56-117">NULL</span><span class="sxs-lookup"><span data-stu-id="32d56-117">NULL</span></span>|<span data-ttu-id="32d56-118">false</span><span class="sxs-lookup"><span data-stu-id="32d56-118">FALSE</span></span>|<span data-ttu-id="32d56-119">NULL</span><span class="sxs-lookup"><span data-stu-id="32d56-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="32d56-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32d56-120">Example</span></span>  

 <span data-ttu-id="32d56-121">In der folgenden Entity SQL-Abfrage wird die Verwendung des AND-Operators veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="32d56-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="32d56-122">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="32d56-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="32d56-123">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="32d56-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="32d56-124">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="32d56-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="32d56-125">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="32d56-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="32d56-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32d56-126">See also</span></span>

- [<span data-ttu-id="32d56-127">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="32d56-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
