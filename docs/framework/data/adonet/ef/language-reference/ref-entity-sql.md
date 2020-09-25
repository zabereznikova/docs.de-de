---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 56ae576ac60d1716d86fbbb797882bf96e99813f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202239"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="842f2-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="842f2-102">REF (Entity SQL)</span></span>

<span data-ttu-id="842f2-103">Gibt einen Verweis auf eine Entitätsinstanz zurück.</span><span class="sxs-lookup"><span data-stu-id="842f2-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="842f2-104">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="842f2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="842f2-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="842f2-106">Gültige Ausdrücke, die eine Instanz eines Entitätstyps zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="842f2-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="842f2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="842f2-107">Return Value</span></span>  

 <span data-ttu-id="842f2-108">Ein Verweis auf die angegebene Entitätsinstanz.</span><span class="sxs-lookup"><span data-stu-id="842f2-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="842f2-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="842f2-109">Remarks</span></span>  

 <span data-ttu-id="842f2-110">Ein Entitätsverweis besteht aus dem Entitätsschlüssel und einem Entitätenmengennamen.</span><span class="sxs-lookup"><span data-stu-id="842f2-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="842f2-111">Da unterschiedliche Entitätenmengen auf demselben Typ basieren können, kann ein bestimmter Entitätsschlüssel in mehreren Entitätenmengen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="842f2-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="842f2-112">Ein Entitätsverweis ist jedoch stets eindeutig.</span><span class="sxs-lookup"><span data-stu-id="842f2-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="842f2-113">Wenn der Eingabeausdruck eine permanente Entität darstellt, wird ein Verweis auf diese Entität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="842f2-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="842f2-114">Wenn der Eingabeausdruck keine permanente Entität ist, wird ein NULL-Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="842f2-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="842f2-115">Wird der Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft verwendet, wird der Verweis automatisch dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="842f2-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842f2-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="842f2-116">Example</span></span>  

 <span data-ttu-id="842f2-117">Die folgende Entity SQL-Abfrage verwendet den REF-Operator, um den Verweis für ein Eingabeentitätsargument zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="842f2-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="842f2-118">Dieselbe Abfrage dereferenziert den Verweis, da ein Eigenschaftsextraktionsoperator (.) für den Zugriff auf eine Eigenschaft der "Product"-Entität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="842f2-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="842f2-119">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="842f2-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="842f2-120">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="842f2-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="842f2-121">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="842f2-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="842f2-122">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="842f2-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="842f2-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="842f2-123">See also</span></span>

- [<span data-ttu-id="842f2-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="842f2-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="842f2-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="842f2-125">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="842f2-126">KEY</span><span class="sxs-lookup"><span data-stu-id="842f2-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="842f2-127">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="842f2-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="842f2-128">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="842f2-128">Type Definitions</span></span>](type-definitions-entity-sql.md)
