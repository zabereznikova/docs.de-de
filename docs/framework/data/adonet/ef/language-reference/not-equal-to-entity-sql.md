---
title: '!= (Ungleich) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: bebe85072f5a2cf6a133b88c6d3f5c97299aa63f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191774"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="de4fa-102">!= (Ungleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="de4fa-102">!= (Not Equal To) (Entity SQL)</span></span>

<span data-ttu-id="de4fa-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob sich der linke Ausdruck vom rechten Ausdruck unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="de4fa-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="de4fa-104">Die Funktionsweise des Operators "!=" (Ungleich) ist dieselbe wie die des Operators <>.</span><span class="sxs-lookup"><span data-stu-id="de4fa-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4fa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="de4fa-105">Syntax</span></span>  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="de4fa-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="de4fa-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="de4fa-107">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de4fa-107">Any valid expression.</span></span> <span data-ttu-id="de4fa-108">Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen.</span><span class="sxs-lookup"><span data-stu-id="de4fa-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="de4fa-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="de4fa-109">Result Types</span></span>  

 <span data-ttu-id="de4fa-110">`true` , wenn der linke Ausdruck ungleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="de4fa-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de4fa-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de4fa-111">Example</span></span>  

 <span data-ttu-id="de4fa-112">In der folgenden Entity SQL-Abfrage wird der Operator "!=" verwendet, um zu ermitteln, ob der linke Ausdruck ungleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="de4fa-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="de4fa-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="de4fa-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="de4fa-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="de4fa-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="de4fa-115">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="de4fa-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="de4fa-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="de4fa-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="de4fa-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de4fa-117">See also</span></span>

- [<span data-ttu-id="de4fa-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="de4fa-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
