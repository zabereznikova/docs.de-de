---
title: '>= (Größer als oder gleich) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 4b7b2aa7be0b978fb6b1317393fb3c6e9a87c621
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289011"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="39d6e-102">>= (Größer als oder gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="39d6e-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="39d6e-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="39d6e-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39d6e-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="39d6e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="39d6e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="39d6e-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39d6e-106">Any valid expression.</span></span> <span data-ttu-id="39d6e-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="39d6e-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="39d6e-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="39d6e-108">Result Types</span></span>  
 <span data-ttu-id="39d6e-109">`true` , wenn der linke Ausdruck größer oder gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="39d6e-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39d6e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39d6e-110">Example</span></span>  
 <span data-ttu-id="39d6e-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator >= verwendet, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="39d6e-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="39d6e-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="39d6e-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="39d6e-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="39d6e-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="39d6e-114">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="39d6e-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="39d6e-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="39d6e-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="39d6e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39d6e-116">See also</span></span>
- [<span data-ttu-id="39d6e-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="39d6e-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
