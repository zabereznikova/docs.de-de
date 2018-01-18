---
title: '- (Division) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5f9f640d50ec24b30cedfe0d4d8d4982509efc35
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="53040-102">/ (Division) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="53040-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="53040-103">Dividiert eine Zahl durch eine andere.</span><span class="sxs-lookup"><span data-stu-id="53040-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53040-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53040-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="53040-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="53040-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="53040-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="53040-106">The numeric expression to divide.</span></span> <span data-ttu-id="53040-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="53040-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="53040-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="53040-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="53040-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="53040-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="53040-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="53040-110">Result Types</span></span>  
 <span data-ttu-id="53040-111">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="53040-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="53040-112">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="53040-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53040-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53040-113">Example</span></span>  
 <span data-ttu-id="53040-114">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "/", um eine Zahl durch eine andere zu dividieren.</span><span class="sxs-lookup"><span data-stu-id="53040-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="53040-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="53040-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="53040-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="53040-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="53040-117">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="53040-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="53040-118">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="53040-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="53040-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53040-119">See Also</span></span>  
 [<span data-ttu-id="53040-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="53040-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
