---
title: '- Negative (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204410"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="72aac-102">- (Negativ) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="72aac-102">- (Negative) (Entity SQL)</span></span>

<span data-ttu-id="72aac-103">Gibt den negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="72aac-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72aac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72aac-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="72aac-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="72aac-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="72aac-106">Jeder gültige Ausdruck mit einem numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="72aac-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="72aac-107">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="72aac-107">Result Types</span></span>  

 <span data-ttu-id="72aac-108">Der Datentyp von `expression`.</span><span class="sxs-lookup"><span data-stu-id="72aac-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72aac-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="72aac-109">Remarks</span></span>  

 <span data-ttu-id="72aac-110">Wenn `expression` ein Typ ohne Vorzeichen ist, ist der Ergebnistyp der Typ mit Vorzeichen, der dem Typ von `expression`am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="72aac-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="72aac-111">Wenn z. B. `expression` vom Typ "Byte" ist, wird ein Wert vom Typ "Int16" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="72aac-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72aac-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72aac-112">Example</span></span>  

 <span data-ttu-id="72aac-113">Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "-", um den negativen Wert eines numerischen Ausdrucks zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="72aac-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="72aac-114">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="72aac-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="72aac-115">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="72aac-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="72aac-116">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="72aac-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="72aac-117">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="72aac-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="72aac-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72aac-118">See also</span></span>

- [<span data-ttu-id="72aac-119">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="72aac-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
