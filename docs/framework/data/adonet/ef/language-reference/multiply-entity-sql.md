---
title: '* Lik (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 3dd77270e6765a0431dc473bbbcadeb6481a4699
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175654"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="98a3d-102">\* (Multiplikation) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="98a3d-102">\* (Multiply) (Entity SQL)</span></span>

<span data-ttu-id="98a3d-103">Multipliziert zwei Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="98a3d-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98a3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98a3d-104">Syntax</span></span>  
  
```sql  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="98a3d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="98a3d-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="98a3d-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="98a3d-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="98a3d-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="98a3d-107">Result Types</span></span>  

 <span data-ttu-id="98a3d-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="98a3d-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="98a3d-109">Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="98a3d-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98a3d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98a3d-110">Example</span></span>  

 <span data-ttu-id="98a3d-111">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "\*", um zwei Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="98a3d-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="98a3d-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="98a3d-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="98a3d-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="98a3d-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="98a3d-114">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="98a3d-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="98a3d-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="98a3d-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MULTIPLY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="98a3d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98a3d-116">See also</span></span>

- [<span data-ttu-id="98a3d-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="98a3d-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
