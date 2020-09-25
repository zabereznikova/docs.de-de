---
title: Modulo (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 25bd34db3a627fa708e1ab9a3f0e237426487bcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175706"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="302a0-102">Modulo (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="302a0-102">(Modulo) (Entity SQL)</span></span>

<span data-ttu-id="302a0-103">Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.</span><span class="sxs-lookup"><span data-stu-id="302a0-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="302a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="302a0-104">Syntax</span></span>  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="302a0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="302a0-105">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="302a0-106">Der zu dividierende numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="302a0-106">The numeric expression to divide.</span></span> <span data-ttu-id="302a0-107">`dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="302a0-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="302a0-108">Der numerische Ausdruck, durch den der Dividend geteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="302a0-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="302a0-109">`divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="302a0-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="302a0-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="302a0-110">Result Types</span></span>  

 <span data-ttu-id="302a0-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="302a0-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="302a0-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="302a0-112">Example</span></span>  

 <span data-ttu-id="302a0-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="302a0-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="302a0-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="302a0-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="302a0-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="302a0-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="302a0-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="302a0-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="302a0-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="302a0-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="302a0-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="302a0-118">See also</span></span>

- [<span data-ttu-id="302a0-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="302a0-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
