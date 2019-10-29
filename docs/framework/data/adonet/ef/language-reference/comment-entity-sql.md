---
title: -- (Kommentar) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 43b8cdbf5dbca8822645c27711f6984b8d741ea7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040288"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="5f998-102">-- (Kommentar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f998-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5f998-103">-Abfragen können Kommentare enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f998-103">queries can contain comments.</span></span> <span data-ttu-id="5f998-104">Zwei Bindestriche (`--`) zeigen den Beginn einer Kommentarzeile an.</span><span class="sxs-lookup"><span data-stu-id="5f998-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f998-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f998-105">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f998-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="5f998-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="5f998-107">Ist die Zeichenfolge mit dem Kommentartext.</span><span class="sxs-lookup"><span data-stu-id="5f998-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f998-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f998-108">Example</span></span>  
 <span data-ttu-id="5f998-109">In der folgenden Entity SQL-Abfrage wird die Verwendung von Kommentaren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5f998-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="5f998-110">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5f998-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5f998-111">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5f998-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5f998-112">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5f998-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5f998-113">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5f998-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="5f998-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f998-114">See also</span></span>

- [<span data-ttu-id="5f998-115">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5f998-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="5f998-116">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5f998-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
