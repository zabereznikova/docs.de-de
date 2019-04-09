---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: f4fa8cbc07513321e59b93503b59af172c0a6f05
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211321"
---
# <a name="in-entity-sql"></a><span data-ttu-id="615bf-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="615bf-102">IN (Entity SQL)</span></span>
<span data-ttu-id="615bf-103">Bestimmt, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="615bf-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="615bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="615bf-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="615bf-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="615bf-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="615bf-106">Jeder gültige Ausdruck, der den auf Übereinstimmung zu prüfenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="615bf-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="615bf-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="615bf-107">[ NOT ]</span></span>  
 <span data-ttu-id="615bf-108">Legt fest, dass das `Boolean`-Ergebnis von IN negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="615bf-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="615bf-109">Jeder gültige Ausdruck, der die auf Übereinstimmung zu prüfende Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="615bf-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="615bf-110">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `value`.</span><span class="sxs-lookup"><span data-stu-id="615bf-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="615bf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="615bf-111">Return Value</span></span>  
 `true` <span data-ttu-id="615bf-112">Wenn der Wert in der Auflistung gefunden wird; NULL, wenn der Wert null ist oder die Auflistung ist null. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="615bf-112">if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="615bf-113">Mit NOT IN wird das Ergebnis von IN negiert.</span><span class="sxs-lookup"><span data-stu-id="615bf-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="615bf-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="615bf-114">Example</span></span>  
 <span data-ttu-id="615bf-115">Die folgende Entity SQL-Abfrage verwendet den IN-Operator, um zu bestimmen, ob ein Wert mit irgendeinem Wert in einer Auflistung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="615bf-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="615bf-116">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="615bf-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="615bf-117">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="615bf-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="615bf-118">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="615bf-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="615bf-119">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="615bf-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="615bf-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="615bf-120">See also</span></span>

- [<span data-ttu-id="615bf-121">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="615bf-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
