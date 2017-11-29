---
title: '!= (Ungleich) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2187e317229961b0929f1415cd40f6f65f5c593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="b4844-102">!= (Ungleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b4844-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="b4844-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob sich der linke Ausdruck vom rechten Ausdruck unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="b4844-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="b4844-104">Die Funktionsweise des Operators "!=" (Ungleich) ist dieselbe wie die des Operators <>.</span><span class="sxs-lookup"><span data-stu-id="b4844-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4844-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4844-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4844-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="b4844-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b4844-107">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b4844-107">Any valid expression.</span></span> <span data-ttu-id="b4844-108">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="b4844-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b4844-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="b4844-109">Result Types</span></span>  
 <span data-ttu-id="b4844-110">`true` , wenn der linke Ausdruck ungleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b4844-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4844-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4844-111">Example</span></span>  
 <span data-ttu-id="b4844-112">In der folgenden Entity SQL-Abfrage wird der Operator "!=" verwendet, um zu ermitteln, ob der linke Ausdruck ungleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="b4844-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="b4844-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b4844-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b4844-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b4844-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b4844-115">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b4844-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b4844-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b4844-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="b4844-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4844-117">See Also</span></span>  
 [<span data-ttu-id="b4844-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b4844-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
