---
title: + (Hinzufügen)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 8c9a6b2c8168e4677c37cfdb0b401a93ee0040cf
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251370"
---
# <a name="-add"></a><span data-ttu-id="ac6e3-102">+ (Addition)</span><span class="sxs-lookup"><span data-stu-id="ac6e3-102">+ (Add)</span></span>
<span data-ttu-id="ac6e3-103">Addiert zwei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac6e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac6e3-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac6e3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ac6e3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ac6e3-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ac6e3-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="ac6e3-107">Result Types</span></span>  
 <span data-ttu-id="ac6e3-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ac6e3-109">Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="ac6e3-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac6e3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac6e3-110">Remarks</span></span>  
 <span data-ttu-id="ac6e3-111">Für EDM.String-Typen wird Addition als Verkettung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac6e3-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac6e3-112">Example</span></span>  
 <span data-ttu-id="ac6e3-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator +, um zwei Zahlen zu addieren.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="ac6e3-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ac6e3-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ac6e3-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ac6e3-116">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ac6e3-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ac6e3-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="ac6e3-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="ac6e3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac6e3-118">See also</span></span>

- [<span data-ttu-id="ac6e3-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="ac6e3-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ac6e3-120">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ac6e3-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
