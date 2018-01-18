---
title: IN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d32e5012b4acbf0ecd6830f549de5dccf79bb38b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="in-entity-sql"></a><span data-ttu-id="63659-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="63659-102">IN (Entity SQL)</span></span>
<span data-ttu-id="63659-103">Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="63659-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63659-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63659-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="63659-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="63659-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="63659-106">Jeder gültige Ausdruck, der den auf Übereinstimmung zu prüfenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63659-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="63659-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="63659-107">[ NOT ]</span></span>  
 <span data-ttu-id="63659-108">Legt fest, dass das `Boolean`-Ergebnis von IN negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="63659-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="63659-109">Jeder gültige Ausdruck, der die auf Übereinstimmung zu prüfende Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63659-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="63659-110">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `value`.</span><span class="sxs-lookup"><span data-stu-id="63659-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63659-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63659-111">Return Value</span></span>  
 <span data-ttu-id="63659-112">`true`, wenn der Wert in der Auflistung gefunden wurde, null, wenn der Wert oder die Auflistung NULL ist, anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="63659-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="63659-113">Mit NOT IN wird das Ergebnis von IN negiert.</span><span class="sxs-lookup"><span data-stu-id="63659-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63659-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63659-114">Example</span></span>  
 <span data-ttu-id="63659-115">Die folgende Entity SQL-Abfrage verwendet den IN-Operator, um zu bestimmen, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="63659-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="63659-116">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="63659-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="63659-117">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="63659-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="63659-118">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="63659-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="63659-119">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="63659-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="63659-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63659-120">See Also</span></span>  
 [<span data-ttu-id="63659-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="63659-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
