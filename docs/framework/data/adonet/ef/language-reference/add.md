---
title: + (Hinzufügen)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: a3c41ef8cf393a4d1b1deb362d6a3614558a34ba
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591424"
---
# <a name="-add"></a><span data-ttu-id="7a445-102">+ (Addition)</span><span class="sxs-lookup"><span data-stu-id="7a445-102">+ (Add)</span></span>
<span data-ttu-id="7a445-103">Addiert zwei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="7a445-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a445-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a445-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a445-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7a445-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7a445-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="7a445-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7a445-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="7a445-107">Result Types</span></span>  
 <span data-ttu-id="7a445-108">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="7a445-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="7a445-109">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7a445-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a445-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a445-110">Remarks</span></span>  
 <span data-ttu-id="7a445-111">Für EDM.String-Typen wird Addition als Verkettung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a445-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a445-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a445-112">Example</span></span>  
 <span data-ttu-id="7a445-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator +, um zwei Zahlen zu addieren.</span><span class="sxs-lookup"><span data-stu-id="7a445-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="7a445-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="7a445-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7a445-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7a445-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7a445-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7a445-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7a445-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="7a445-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="7a445-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a445-118">See Also</span></span>  
 [<span data-ttu-id="7a445-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="7a445-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="7a445-120">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="7a445-120">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
