---
title: '* (Multiplizieren) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e2dca4be3d23d6cf9171eec960335ef57de1156c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="b07f9-102">* (Multiplikation) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b07f9-102">* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="b07f9-103">Multipliziert zwei Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="b07f9-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b07f9-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b07f9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b07f9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b07f9-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b07f9-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b07f9-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="b07f9-107">Result Types</span></span>  
 <span data-ttu-id="b07f9-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="b07f9-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="b07f9-109">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b07f9-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b07f9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b07f9-110">Example</span></span>  
 <span data-ttu-id="b07f9-111">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "*", um zwei Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="b07f9-111">The following Entity SQL query uses the * arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="b07f9-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b07f9-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b07f9-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b07f9-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b07f9-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b07f9-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b07f9-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b07f9-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="b07f9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b07f9-116">See Also</span></span>  
 [<span data-ttu-id="b07f9-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b07f9-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
