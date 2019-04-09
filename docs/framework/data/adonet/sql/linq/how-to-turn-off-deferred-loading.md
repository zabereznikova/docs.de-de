---
title: 'Vorgehensweise: Deaktivieren des verzögerten Ladens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f82e347ecdb3c69cee3749855d1e4cb457a460f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112956"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="4df53-102">Vorgehensweise: Deaktivieren des verzögerten Ladens</span><span class="sxs-lookup"><span data-stu-id="4df53-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="4df53-103">Sie können verzögertes Laden ausschalten, indem Sie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="4df53-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="4df53-104">Weitere Informationen finden Sie unter [verzögertes im Vergleich zu den sofortigen Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="4df53-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4df53-105">Verzögertes Laden wird ausgeschaltet, wenn die Objektverfolgung ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4df53-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="4df53-106">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Informationen als nur-Lese](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="4df53-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4df53-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4df53-107">Example</span></span>  
 <span data-ttu-id="4df53-108">Im folgenden Beispiel wird gezeigt, wie verzögertes Laden durch Festlegen von <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4df53-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4df53-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4df53-109">See also</span></span>

- [<span data-ttu-id="4df53-110">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="4df53-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="4df53-111">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="4df53-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
