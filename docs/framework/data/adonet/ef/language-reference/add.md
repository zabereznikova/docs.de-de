---
title: + (Hinzufügen)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b86d273658362c3bb204d5220ff5e9db1f8de9fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198053"
---
# <a name="-add"></a><span data-ttu-id="f0861-102">+ (Addition)</span><span class="sxs-lookup"><span data-stu-id="f0861-102">+ (Add)</span></span>

<span data-ttu-id="f0861-103">Addition zweier Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f0861-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0861-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0861-104">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0861-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f0861-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="f0861-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="f0861-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f0861-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="f0861-107">Result Types</span></span>  

 <span data-ttu-id="f0861-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="f0861-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="f0861-109">Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="f0861-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0861-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f0861-110">Remarks</span></span>  

 <span data-ttu-id="f0861-111">Für EDM.String-Typen wird Addition als Verkettung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0861-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0861-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0861-112">Example</span></span>  

 <span data-ttu-id="f0861-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator +, um zwei Zahlen zu addieren.</span><span class="sxs-lookup"><span data-stu-id="f0861-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="f0861-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="f0861-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f0861-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f0861-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f0861-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f0861-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f0861-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="f0861-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="f0861-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0861-118">See also</span></span>

- [<span data-ttu-id="f0861-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="f0861-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f0861-120">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="f0861-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
