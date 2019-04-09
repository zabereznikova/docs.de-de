---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 820d357baf8f3e17a10ced84babc6745512e572b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230030"
---
# <a name="key-entity-sql"></a><span data-ttu-id="55727-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="55727-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="55727-103">Extrahiert den Schlüssel eines Verweises oder eines Entitätsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="55727-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55727-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55727-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="55727-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55727-105">Remarks</span></span>  
 <span data-ttu-id="55727-106">Ein Entitätsschlüssel enthält in korrekter Reihenfolge die Schlüsselwerte der angegebenen Entität oder des Entitätsverweises.</span><span class="sxs-lookup"><span data-stu-id="55727-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="55727-107">Da viele Entitätenmengen auf demselben Typ basieren können, kann derselbe Schlüssel in jeder Entitätenmenge vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="55727-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="55727-108">Um einen eindeutigen Verweis abzurufen, verwenden Sie `REF`.</span><span class="sxs-lookup"><span data-stu-id="55727-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="55727-109">Der Rückgabetyp des KEY-Operators ist ein Zeilentyp, der ein Feld für jeden Schlüssel der Entität in der gleichen Reihenfolge beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="55727-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="55727-110">Im folgenden Beispiel wird dem KEY-Operator ein Verweis auf die BadOrder-Entität übergeben, und er gibt den Schlüsselteil dieses Verweises zurück.</span><span class="sxs-lookup"><span data-stu-id="55727-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="55727-111">In diesem Fall einen Datensatztyp mit genau einem Feld, das der `Id` -Eigenschaft entspricht.</span><span class="sxs-lookup"><span data-stu-id="55727-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="55727-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55727-112">Example</span></span>  
 <span data-ttu-id="55727-113">Die folgende Entity SQL-Abfrage verwendet den KEY-Operator, um den Schlüsselteil eines Ausdrucks mit Typverweis zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="55727-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="55727-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="55727-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="55727-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="55727-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="55727-116">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="55727-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="55727-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="55727-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="55727-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55727-118">See also</span></span>

- [<span data-ttu-id="55727-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="55727-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="55727-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="55727-120">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="55727-121">REF</span><span class="sxs-lookup"><span data-stu-id="55727-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [<span data-ttu-id="55727-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="55727-122">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
