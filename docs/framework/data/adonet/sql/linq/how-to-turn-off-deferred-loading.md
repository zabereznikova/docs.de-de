---
title: 'Vorgehensweise: Schalten Sie verzögertes Laden aus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 9878ec468333ba79d0171d0bf96235d48273e03e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669535"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="8d2e5-102">Vorgehensweise: Schalten Sie verzögertes Laden aus</span><span class="sxs-lookup"><span data-stu-id="8d2e5-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="8d2e5-103">Sie können verzögertes Laden ausschalten, indem Sie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8d2e5-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="8d2e5-104">Weitere Informationen finden Sie unter [verzögertes im Vergleich zu den sofortigen Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="8d2e5-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d2e5-105">Verzögertes Laden wird ausgeschaltet, wenn die Objektverfolgung ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="8d2e5-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="8d2e5-106">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Informationen als nur-Lese](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="8d2e5-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d2e5-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d2e5-107">Example</span></span>  
 <span data-ttu-id="8d2e5-108">Im folgenden Beispiel wird gezeigt, wie verzögertes Laden durch Festlegen von <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="8d2e5-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8d2e5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d2e5-109">See also</span></span>
- [<span data-ttu-id="8d2e5-110">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="8d2e5-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="8d2e5-111">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="8d2e5-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
