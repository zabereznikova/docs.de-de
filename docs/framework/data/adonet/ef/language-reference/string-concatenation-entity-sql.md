---
title: + (Zeichen folgen Verkettung) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: ef482a1206dea98cfb5a0ba5071acc130ef0cd18
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249033"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="71c81-102">+ (Zeichenfolgenverkettung) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="71c81-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="71c81-103">Verkettet zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="71c81-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71c81-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="71c81-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="71c81-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="71c81-106">Jeder gültige Ausdruck des Datentyps EDM.String.</span><span class="sxs-lookup"><span data-stu-id="71c81-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="71c81-107">Beide Ausdrücke müssen denselben Datentyp aufweisen, oder ein Ausdruck muss implizit in den Datentyp des anderen Ausdrucks konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="71c81-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="71c81-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="71c81-108">Result Types</span></span>  
 <span data-ttu-id="71c81-109">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="71c81-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="71c81-110">Weitere Informationen zur impliziten herauf Stufung von Typen finden Sie unter [Type System (Typsystem](type-system-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="71c81-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71c81-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71c81-111">Example</span></span>  
 <span data-ttu-id="71c81-112">Die folgende Entity SQL-Abfrage verwendet den Operator "+", um zwei Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="71c81-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="71c81-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="71c81-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="71c81-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="71c81-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="71c81-115">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="71c81-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="71c81-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="71c81-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="71c81-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71c81-117">See also</span></span>

- [<span data-ttu-id="71c81-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="71c81-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="71c81-119">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="71c81-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
