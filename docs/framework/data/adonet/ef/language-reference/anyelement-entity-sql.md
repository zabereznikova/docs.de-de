---
title: ANYELEMENT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de08e590bcc7b2380f2edda0ebc918d7ce328f4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="cdfc4-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cdfc4-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="cdfc4-103">Extrahiert ein Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdfc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdfc4-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdfc4-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cdfc4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cdfc4-106">Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, aus der ein Element extrahiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdfc4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cdfc4-107">Return Value</span></span>  
 <span data-ttu-id="cdfc4-108">Ein einzelnes Element in der Auflistung oder ein beliebiges Element, sofern die Auflistung über verschiedene Elemente verfügt. Wenn die Auflistung leer ist, wird `null`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="cdfc4-109">Wenn `collection` ist eine Auflistung vom Typ `Collection<T>`, klicken Sie dann `ANYELEMENT(collection)` ist ein gültiger Ausdruck, der eine Instanz des Typs ergibt `T`.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdfc4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdfc4-110">Remarks</span></span>  
 <span data-ttu-id="cdfc4-111">ANYELEMENT extrahiert ein beliebiges Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="cdfc4-112">Im folgenden Beispiel soll ein Singleton-Element aus dem Satz `Customers`extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="cdfc4-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdfc4-113">Example</span></span>  
 <span data-ttu-id="cdfc4-114">Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage extrahiert mithilfe des ANYELEMENT-Operators ein Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="cdfc4-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="cdfc4-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cdfc4-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cdfc4-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cdfc4-117">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cdfc4-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cdfc4-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="cdfc4-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="cdfc4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdfc4-119">See Also</span></span>  
 [<span data-ttu-id="cdfc4-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="cdfc4-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="cdfc4-121">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="cdfc4-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
