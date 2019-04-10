---
title: (Modulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: e2d2c4cd6fd62cf5785d6b69aa399a74f8d04d30
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326735"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="d432e-102">(Modulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d432e-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="d432e-103">Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.</span><span class="sxs-lookup"><span data-stu-id="d432e-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d432e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d432e-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="d432e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d432e-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="d432e-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d432e-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="d432e-107">ist jeder gültiger Ausdruck eines beliebigen numerischen Datentyps sein.</span><span class="sxs-lookup"><span data-stu-id="d432e-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="d432e-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d432e-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="d432e-109">ist jeder gültiger Ausdruck eines beliebigen numerischen Datentyps sein.</span><span class="sxs-lookup"><span data-stu-id="d432e-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d432e-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="d432e-110">Result Types</span></span>  
 <span data-ttu-id="d432e-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="d432e-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="d432e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d432e-112">Example</span></span>  
 <span data-ttu-id="d432e-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d432e-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="d432e-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d432e-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d432e-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d432e-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d432e-116">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d432e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d432e-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d432e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="d432e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d432e-118">See also</span></span>

- [<span data-ttu-id="d432e-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d432e-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
