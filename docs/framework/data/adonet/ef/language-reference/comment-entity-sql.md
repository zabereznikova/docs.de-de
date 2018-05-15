---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="74475-102">-- (Kommentar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="74475-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="74475-103"> -Abfragen können Kommentare enthalten.</span><span class="sxs-lookup"><span data-stu-id="74475-103"> queries can contain comments.</span></span> <span data-ttu-id="74475-104">Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.</span><span class="sxs-lookup"><span data-stu-id="74475-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74475-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74475-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="74475-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="74475-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="74475-107">Ist die Zeichenfolge mit dem Kommentartext.</span><span class="sxs-lookup"><span data-stu-id="74475-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74475-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74475-108">Example</span></span>  
 <span data-ttu-id="74475-109">In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="74475-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="74475-110">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="74475-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="74475-111">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="74475-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="74475-112">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="74475-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="74475-113">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="74475-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="74475-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74475-114">See Also</span></span>  
 [<span data-ttu-id="74475-115">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="74475-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="74475-116">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="74475-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
