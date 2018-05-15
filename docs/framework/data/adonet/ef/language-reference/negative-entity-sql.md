---
title: '- (Negativ) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 5d1726be6a4a59891646d05b344f59962d548c75
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="d2bd7-102">- (Negativ) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d2bd7-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="d2bd7-103">Gibt den negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2bd7-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2bd7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d2bd7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d2bd7-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d2bd7-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="d2bd7-107">Result Types</span></span>  
 <span data-ttu-id="d2bd7-108">Der Datentyp von `expression`.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2bd7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2bd7-109">Remarks</span></span>  
 <span data-ttu-id="d2bd7-110">Wenn `expression` ein Typ ohne Vorzeichen ist, ist der Ergebnistyp der Typ mit Vorzeichen, der dem Typ von `expression`am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="d2bd7-111">Wenn z. B. `expression` vom Typ "Byte" ist, wird ein Wert vom Typ "Int16" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2bd7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2bd7-112">Example</span></span>  
 <span data-ttu-id="d2bd7-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "-", um den negativen Wert eines numerischen Ausdrucks zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="d2bd7-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d2bd7-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d2bd7-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d2bd7-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d2bd7-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d2bd7-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d2bd7-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d2bd7-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="d2bd7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2bd7-118">See Also</span></span>  
 [<span data-ttu-id="d2bd7-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d2bd7-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
