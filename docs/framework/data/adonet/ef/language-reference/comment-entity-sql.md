---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 1ea1929b0e6f965f71fbb015ee6795affb3bce7c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251207"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="d0635-102">-- (Kommentar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d0635-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="d0635-103">-Abfragen können Kommentare enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0635-103">queries can contain comments.</span></span> <span data-ttu-id="d0635-104">Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.</span><span class="sxs-lookup"><span data-stu-id="d0635-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0635-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0635-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0635-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="d0635-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="d0635-107">Ist die Zeichenfolge mit dem Kommentartext.</span><span class="sxs-lookup"><span data-stu-id="d0635-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0635-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0635-108">Example</span></span>  
 <span data-ttu-id="d0635-109">In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d0635-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="d0635-110">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d0635-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d0635-111">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d0635-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d0635-112">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0635-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d0635-113">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d0635-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="d0635-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0635-114">See also</span></span>

- [<span data-ttu-id="d0635-115">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d0635-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="d0635-116">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d0635-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
