---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: abe47f8c72abe13bd5c27fe10a412ff94ab861cf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855138"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="60dba-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="60dba-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="60dba-103">Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="60dba-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60dba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60dba-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="60dba-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="60dba-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="60dba-106">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="60dba-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60dba-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60dba-107">Return Value</span></span>  
 <span data-ttu-id="60dba-108">Der Wert der Entität, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="60dba-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60dba-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60dba-109">Remarks</span></span>  
 <span data-ttu-id="60dba-110">Der DEREF-Operator dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="60dba-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="60dba-111">Z. B. wenn `r` ist ein Verweis vom Typ Ref\<T >, `Deref(r)` ist ein Ausdruck vom Typ `T` ergibt die Entität verweist `r`.</span><span class="sxs-lookup"><span data-stu-id="60dba-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="60dba-112">Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht existiert, hat das Ergebnis des DEREF-Operators den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="60dba-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60dba-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60dba-113">Example</span></span>  
 <span data-ttu-id="60dba-114">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der DEREF-Operator verwendet, um einen Verweiswert zu dereferenzieren und das Ergebnis dieser Dereferenzierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60dba-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="60dba-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="60dba-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="60dba-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="60dba-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="60dba-117">Führen Sie die Verfahren in [wie: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="60dba-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="60dba-118">Übergeben Sie die folgende Abfrage als Argument an die ExecutePrimitiveTypeQuery-Methode:</span><span class="sxs-lookup"><span data-stu-id="60dba-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="60dba-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60dba-119">See Also</span></span>  
 [<span data-ttu-id="60dba-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="60dba-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="60dba-121">REF</span><span class="sxs-lookup"><span data-stu-id="60dba-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="60dba-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="60dba-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="60dba-123">KEY</span><span class="sxs-lookup"><span data-stu-id="60dba-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="60dba-124">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="60dba-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
