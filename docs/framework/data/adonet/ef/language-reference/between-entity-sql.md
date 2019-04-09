---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225260"
---
# <a name="between-entity-sql"></a><span data-ttu-id="bae98-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bae98-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="bae98-103">Ermittelt, ob der Ergebniswert eines Ausdrucks in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="bae98-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="bae98-104">Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN-Ausdruck hat die gleiche Funktionalität wie die Transact-SQL-BETWEEN-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bae98-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bae98-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="bae98-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="bae98-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bae98-107">Jeder zu testende gültige Ausdruck im Bereich, der durch `begin_expression` und `end_expression` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bae98-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> `expression` <span data-ttu-id="bae98-108">muss vom gleiche Typ sein wie `begin_expression` und `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bae98-108">must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="bae98-109">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bae98-109">Any valid expression.</span></span> `begin_expression` <span data-ttu-id="bae98-110">muss vom gleiche Typ sein wie `expression` und `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bae98-110">must be the same type as both `expression` and `end_expression`.</span></span> `begin_expression` <span data-ttu-id="bae98-111">muss kleiner als `end_expression`, andernfalls wird der Rückgabewert negiert.</span><span class="sxs-lookup"><span data-stu-id="bae98-111">should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="bae98-112">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bae98-112">Any valid expression.</span></span> `end_expression` <span data-ttu-id="bae98-113">muss vom gleiche Typ sein wie `expression` und `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="bae98-113">must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="bae98-114">NICHT</span><span class="sxs-lookup"><span data-stu-id="bae98-114">NOT</span></span>  
 <span data-ttu-id="bae98-115">Gibt an, dass das Ergebnis von BETWEEN negiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bae98-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="bae98-116">UND</span><span class="sxs-lookup"><span data-stu-id="bae98-116">AND</span></span>  
 <span data-ttu-id="bae98-117">Dient als Platzhalter, der anzeigt, dass sich `expression` in dem durch `begin_expression` und `end_expression` festgelegten Bereich befinden soll.</span><span class="sxs-lookup"><span data-stu-id="bae98-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bae98-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bae98-118">Return Value</span></span>  
 `true` <span data-ttu-id="bae98-119">Wenn `expression` zwischen durch den Bereich `begin_expression` und `end_expression`ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="bae98-119">if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> `null` <span data-ttu-id="bae98-120">wird zurückgegeben, wenn `expression` ist `null` oder, wenn `begin_expression` oder `end_expression` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="bae98-120">will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae98-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bae98-121">Remarks</span></span>  
 <span data-ttu-id="bae98-122">Um einen Exklusivbereich anzugeben, verwenden Sie die größer als (>) und kleiner-als-Operatoren (<) anstelle von BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="bae98-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae98-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bae98-123">Example</span></span>  
 <span data-ttu-id="bae98-124">In der folgenden Entity SQL-Abfrage wird der BETWEEN-Operator verwendet, um zu ermitteln, ob der Ergebniswert einer Abfrage in einem angegebenen Bereich liegt.</span><span class="sxs-lookup"><span data-stu-id="bae98-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="bae98-125">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="bae98-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bae98-126">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="bae98-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="bae98-127">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bae98-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="bae98-128">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="bae98-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="bae98-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bae98-129">See also</span></span>

- [<span data-ttu-id="bae98-130">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="bae98-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
