---
title: '&gt; (Größer als) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 1449af09022a9e11be1f3627023318270adf0121
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736928"
---
# <a name="gt-greater-than-entity-sql"></a><span data-ttu-id="9877c-102">&gt; (Größer als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9877c-102">&gt; (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="9877c-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="9877c-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9877c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9877c-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9877c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9877c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9877c-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9877c-106">Any valid expression.</span></span> <span data-ttu-id="9877c-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="9877c-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9877c-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="9877c-108">Result Types</span></span>  
 <span data-ttu-id="9877c-109">`true` , wenn der linke Ausdruck größer als der rechte Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9877c-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9877c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9877c-110">Example</span></span>  
 <span data-ttu-id="9877c-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator > verwendet, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="9877c-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="9877c-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="9877c-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9877c-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="9877c-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9877c-114">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9877c-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9877c-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="9877c-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="9877c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9877c-116">See also</span></span>
- [<span data-ttu-id="9877c-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9877c-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
