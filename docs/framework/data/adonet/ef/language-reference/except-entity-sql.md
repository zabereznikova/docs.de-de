---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: c4df8c2b72ee60a425c98c64a13a1e2d43d4506e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833860"
---
# <a name="except-entity-sql"></a><span data-ttu-id="26ab2-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="26ab2-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="26ab2-103">Gibt eine Auflistung der vom Abfrageausdruck auf der linken Seite des EXCEPT-Operanden zurückgegebenen und unterschiedlichen Werte zurück, die nicht zusätzlich vom Abfrageausdruck auf der rechten Seite des EXCEPT-Operanden zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="26ab2-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="26ab2-104">Alle Ausdrücke müssen vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ sein wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="26ab2-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ab2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26ab2-105">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="26ab2-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="26ab2-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="26ab2-107">Ein beliebiger gültiger Ausdruck, der eine Auflistung für den Vergleich mit einer von einem anderen Abfrageausdruck zurückgegebenen Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="26ab2-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26ab2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="26ab2-108">Return Value</span></span>  
 <span data-ttu-id="26ab2-109">Eine Auflistung vom selben Typ oder vom gleichen Basistyp bzw. abgeleiteten Typ wie `expression`.</span><span class="sxs-lookup"><span data-stu-id="26ab2-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26ab2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26ab2-110">Remarks</span></span>  
 <span data-ttu-id="26ab2-111">EXCEPT ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="26ab2-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="26ab2-112">Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="26ab2-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="26ab2-113">In der folgenden Tabelle wird die Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren dargestellt.</span><span class="sxs-lookup"><span data-stu-id="26ab2-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="26ab2-114">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="26ab2-114">Precedence</span></span>|<span data-ttu-id="26ab2-115">Operatoren</span><span class="sxs-lookup"><span data-stu-id="26ab2-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="26ab2-116">Am höchsten</span><span class="sxs-lookup"><span data-stu-id="26ab2-116">Highest</span></span>|<span data-ttu-id="26ab2-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="26ab2-117">INTERSECT</span></span>|  
||<span data-ttu-id="26ab2-118">UNION</span><span class="sxs-lookup"><span data-stu-id="26ab2-118">UNION</span></span><br /><br /> <span data-ttu-id="26ab2-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="26ab2-119">UNION ALL</span></span>|  
||<span data-ttu-id="26ab2-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="26ab2-120">EXCEPT</span></span>|  
|<span data-ttu-id="26ab2-121">Am niedrigsten</span><span class="sxs-lookup"><span data-stu-id="26ab2-121">Lowest</span></span>|<span data-ttu-id="26ab2-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="26ab2-122">EXISTS</span></span><br /><br /> <span data-ttu-id="26ab2-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="26ab2-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="26ab2-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="26ab2-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="26ab2-125">SET</span><span class="sxs-lookup"><span data-stu-id="26ab2-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26ab2-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26ab2-126">Example</span></span>  
 <span data-ttu-id="26ab2-127">In der folgenden Entity SQL-Abfrage wird ein EXCEPT-Operator verwendet, um eine Auflistung aller unterschiedlicher Werte von zwei Abfrageausdrücken zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="26ab2-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="26ab2-128">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="26ab2-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="26ab2-129">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="26ab2-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="26ab2-130">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="26ab2-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="26ab2-131">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="26ab2-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="26ab2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26ab2-132">See also</span></span>

- [<span data-ttu-id="26ab2-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="26ab2-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
