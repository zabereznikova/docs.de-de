---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: ee3877ca256eb3847b0284ac2a7362a4a60aad48
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deref-entity-sql"></a><span data-ttu-id="4182c-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4182c-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="4182c-103">Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="4182c-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4182c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4182c-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="4182c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4182c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4182c-106">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4182c-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4182c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4182c-107">Return Value</span></span>  
 <span data-ttu-id="4182c-108">Der Wert der Entität, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4182c-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4182c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4182c-109">Remarks</span></span>  
 <span data-ttu-id="4182c-110">Der DEREF-Operator dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="4182c-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="4182c-111">Z. B. wenn `r` ist ein Verweis vom Typ Ref\<T >, `Deref``(r)` ist ein Ausdruck vom Typ `T` , ergeben, dass die Entität verweist `r`.</span><span class="sxs-lookup"><span data-stu-id="4182c-111">For example, if `r` is a reference of type ref\<T>, `Deref``(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="4182c-112">Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht existiert, hat das Ergebnis des DEREF-Operators den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="4182c-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4182c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4182c-113">Example</span></span>  
 <span data-ttu-id="4182c-114">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der DEREF-Operator verwendet, um einen Verweiswert zu dereferenzieren und das Ergebnis dieser Dereferenzierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4182c-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="4182c-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="4182c-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4182c-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="4182c-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4182c-117">Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4182c-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="4182c-118">Übergeben Sie die folgende Abfrage als Argument an die ExecutePrimitiveTypeQuery-Methode:</span><span class="sxs-lookup"><span data-stu-id="4182c-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="4182c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4182c-119">See Also</span></span>  
 [<span data-ttu-id="4182c-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="4182c-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="4182c-121">REF</span><span class="sxs-lookup"><span data-stu-id="4182c-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="4182c-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="4182c-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="4182c-123">KEY</span><span class="sxs-lookup"><span data-stu-id="4182c-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="4182c-124">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="4182c-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
