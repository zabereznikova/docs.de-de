---
title: + (Verketten von Zeichenfolgen) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 24591b54af97eaad705e4914764c7b2c21e5ed0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="2822e-102">+ (Zeichenfolgenverkettung) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2822e-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="2822e-103">Verkettet zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2822e-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2822e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2822e-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2822e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2822e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2822e-106">Jeder gültige Ausdruck des Datentyps EDM.String.</span><span class="sxs-lookup"><span data-stu-id="2822e-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="2822e-107">Beide Ausdrücke müssen denselben Datentyp aufweisen, oder ein Ausdruck muss implizit in den Datentyp des anderen Ausdrucks konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="2822e-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2822e-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="2822e-108">Result Types</span></span>  
 <span data-ttu-id="2822e-109">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="2822e-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="2822e-110">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2822e-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2822e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2822e-111">Example</span></span>  
 <span data-ttu-id="2822e-112">Die folgende Entity SQL-Abfrage verwendet den Operator "+", um zwei Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="2822e-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="2822e-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="2822e-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2822e-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2822e-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2822e-115">Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2822e-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="2822e-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="2822e-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="2822e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2822e-117">See Also</span></span>  
 [<span data-ttu-id="2822e-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="2822e-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="2822e-119">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="2822e-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
