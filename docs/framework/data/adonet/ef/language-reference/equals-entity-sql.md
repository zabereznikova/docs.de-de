---
title: = (Gleich) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 27faf6c59afd4de2481f474053812b12182e3f58
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="b959b-102">= (Gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b959b-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="b959b-103">Überprüft zwei Ausdrücke auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="b959b-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b959b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b959b-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b959b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b959b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b959b-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b959b-106">Any valid expression.</span></span> <span data-ttu-id="b959b-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="b959b-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b959b-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="b959b-108">Result Types</span></span>  
 <span data-ttu-id="b959b-109">`true` , wenn der linke Ausdruck gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b959b-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b959b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b959b-110">Remarks</span></span>  
 <span data-ttu-id="b959b-111">Der Operator "==" ist äquivalent zum Operator "=".</span><span class="sxs-lookup"><span data-stu-id="b959b-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b959b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b959b-112">Example</span></span>  
 <span data-ttu-id="b959b-113">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b959b-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="b959b-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b959b-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b959b-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b959b-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b959b-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b959b-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b959b-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b959b-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="b959b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b959b-118">See Also</span></span>  
 [<span data-ttu-id="b959b-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b959b-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
