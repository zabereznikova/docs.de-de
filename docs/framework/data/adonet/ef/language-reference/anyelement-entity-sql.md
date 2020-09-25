---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: e060956545ca924fa6fedb80b2f53ff312f307a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201199"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="c8bb8-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c8bb8-102">ANYELEMENT (Entity SQL)</span></span>

<span data-ttu-id="c8bb8-103">Extrahiert ein Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8bb8-104">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8bb8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c8bb8-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="c8bb8-106">Jeder gültige, eine Auflistung zurückgebende Abfrageausdruck, aus der ein Element extrahiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8bb8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8bb8-107">Return Value</span></span>  

 <span data-ttu-id="c8bb8-108">Ein einzelnes Element in der Auflistung oder ein beliebiges Element, sofern die Auflistung über verschiedene Elemente verfügt. Wenn die Auflistung leer ist, wird `null`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="c8bb8-109">Wenn `collection` eine Auflistung vom Typ ist `Collection<T>` , dann `ANYELEMENT(collection)` ist ein gültiger Ausdruck, der eine Instanz vom Typ ergibt `T` .</span><span class="sxs-lookup"><span data-stu-id="c8bb8-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8bb8-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8bb8-110">Remarks</span></span>  

 <span data-ttu-id="c8bb8-111">ANYELEMENT extrahiert ein beliebiges Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="c8bb8-112">Im folgenden Beispiel soll ein Singleton-Element aus dem Satz `Customers`extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="c8bb8-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8bb8-113">Example</span></span>  

 <span data-ttu-id="c8bb8-114">Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage extrahiert mithilfe des ANYELEMENT-Operators ein Element aus einer mehrwertigen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="c8bb8-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="c8bb8-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c8bb8-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c8bb8-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c8bb8-117">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c8bb8-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c8bb8-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="c8bb8-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="c8bb8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8bb8-119">See also</span></span>

- [<span data-ttu-id="c8bb8-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="c8bb8-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="c8bb8-121">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="c8bb8-121">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
