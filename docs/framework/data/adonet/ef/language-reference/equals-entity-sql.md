---
title: = (Gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: d50ede1964f6d6b9025a7214efe90e878aa55a0c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333157"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="2d197-102">= (Gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2d197-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="2d197-103">Überprüft zwei Ausdrücke auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="2d197-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d197-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d197-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d197-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2d197-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2d197-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2d197-106">Any valid expression.</span></span> <span data-ttu-id="2d197-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="2d197-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2d197-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="2d197-108">Result Types</span></span>  
 `true` <span data-ttu-id="2d197-109">Wenn der linke Ausdruck ungleich dem rechten Ausdruck ist. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2d197-109">if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d197-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d197-110">Remarks</span></span>  
 <span data-ttu-id="2d197-111">Der Operator "==" ist äquivalent zum Operator "=".</span><span class="sxs-lookup"><span data-stu-id="2d197-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d197-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d197-112">Example</span></span>  
 <span data-ttu-id="2d197-113">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2d197-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="2d197-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="2d197-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2d197-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2d197-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2d197-116">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2d197-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2d197-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="2d197-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="2d197-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d197-118">See also</span></span>

- [<span data-ttu-id="2d197-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="2d197-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
