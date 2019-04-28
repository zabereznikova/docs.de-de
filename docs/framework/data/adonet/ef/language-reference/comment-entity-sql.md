---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605989"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="05f3d-102">-- (Kommentar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="05f3d-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="05f3d-103">-Abfragen können Kommentare enthalten.</span><span class="sxs-lookup"><span data-stu-id="05f3d-103">queries can contain comments.</span></span> <span data-ttu-id="05f3d-104">Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.</span><span class="sxs-lookup"><span data-stu-id="05f3d-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f3d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05f3d-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="05f3d-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="05f3d-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="05f3d-107">Ist die Zeichenfolge mit dem Kommentartext.</span><span class="sxs-lookup"><span data-stu-id="05f3d-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05f3d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05f3d-108">Example</span></span>  
 <span data-ttu-id="05f3d-109">In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="05f3d-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="05f3d-110">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="05f3d-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="05f3d-111">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="05f3d-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="05f3d-112">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="05f3d-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="05f3d-113">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="05f3d-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="05f3d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05f3d-114">See also</span></span>

- [<span data-ttu-id="05f3d-115">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="05f3d-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="05f3d-116">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="05f3d-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
