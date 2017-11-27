---
title: -- (Kommentar) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1961542e615bbbd99bbc517bdd7d649be3f3ef07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="e03cc-102">-- (Kommentar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e03cc-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e03cc-103"> -Abfragen können Kommentare enthalten.</span><span class="sxs-lookup"><span data-stu-id="e03cc-103"> queries can contain comments.</span></span> <span data-ttu-id="e03cc-104">Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.</span><span class="sxs-lookup"><span data-stu-id="e03cc-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03cc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e03cc-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="e03cc-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="e03cc-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="e03cc-107">Ist die Zeichenfolge mit dem Kommentartext.</span><span class="sxs-lookup"><span data-stu-id="e03cc-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03cc-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e03cc-108">Example</span></span>  
 <span data-ttu-id="e03cc-109">In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e03cc-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="e03cc-110">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="e03cc-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e03cc-111">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e03cc-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e03cc-112">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e03cc-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e03cc-113">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="e03cc-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="e03cc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e03cc-114">See Also</span></span>  
 [<span data-ttu-id="e03cc-115">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e03cc-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="e03cc-116">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="e03cc-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
