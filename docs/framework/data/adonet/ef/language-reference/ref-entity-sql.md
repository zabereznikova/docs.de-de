---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 05e687f951930d92797a863410181585278b067d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797760"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="98953-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="98953-102">REF (Entity SQL)</span></span>
<span data-ttu-id="98953-103">Gibt einen Verweis auf eine Entitätsinstanz zurück.</span><span class="sxs-lookup"><span data-stu-id="98953-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98953-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98953-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="98953-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="98953-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="98953-106">Gültige Ausdrücke, die eine Instanz eines Entitätstyps zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="98953-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98953-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98953-107">Return Value</span></span>  
 <span data-ttu-id="98953-108">Ein Verweis auf die angegebene Entitätsinstanz.</span><span class="sxs-lookup"><span data-stu-id="98953-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98953-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98953-109">Remarks</span></span>  
 <span data-ttu-id="98953-110">Ein Entitätsverweis besteht aus dem Entitätsschlüssel und einem Entitätenmengennamen.</span><span class="sxs-lookup"><span data-stu-id="98953-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="98953-111">Da unterschiedliche Entitätenmengen auf demselben Typ basieren können, kann ein bestimmter Entitätsschlüssel in mehreren Entitätenmengen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="98953-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="98953-112">Ein Entitätsverweis ist jedoch stets eindeutig.</span><span class="sxs-lookup"><span data-stu-id="98953-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="98953-113">Wenn der Eingabeausdruck eine permanente Entität darstellt, wird ein Verweis auf diese Entität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98953-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="98953-114">Wenn der Eingabeausdruck keine permanente Entität ist, wird ein NULL-Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98953-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="98953-115">Wird der Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft verwendet, wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="98953-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98953-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98953-116">Example</span></span>  
 <span data-ttu-id="98953-117">Die folgende Entity SQL-Abfrage verwendet den REF-Operator, um den Verweis für ein Eingabeentitätsargument zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="98953-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="98953-118">Dieselbe Abfrage dereferenziert den Verweis, da ein Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft der "Product"-Entität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98953-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="98953-119">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="98953-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="98953-120">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="98953-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="98953-121">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="98953-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="98953-122">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="98953-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="98953-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98953-123">See also</span></span>

- [<span data-ttu-id="98953-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="98953-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [<span data-ttu-id="98953-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="98953-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="98953-126">KEY</span><span class="sxs-lookup"><span data-stu-id="98953-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="98953-127">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="98953-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="98953-128">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="98953-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
