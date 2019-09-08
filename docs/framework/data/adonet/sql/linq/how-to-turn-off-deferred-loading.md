---
title: 'Vorgehensweise: Deaktivieren des verzögerten Ladens'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781654"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="3b5cc-102">Vorgehensweise: Deaktivieren des verzögerten Ladens</span><span class="sxs-lookup"><span data-stu-id="3b5cc-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="3b5cc-103">Sie können verzögertes Laden ausschalten, indem Sie <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3b5cc-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="3b5cc-104">Weitere Informationen finden Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="3b5cc-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b5cc-105">Verzögertes Laden wird ausgeschaltet, wenn die Objektverfolgung ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="3b5cc-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="3b5cc-106">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Informationen als](how-to-retrieve-information-as-read-only.md)schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="3b5cc-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b5cc-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b5cc-107">Example</span></span>  
 <span data-ttu-id="3b5cc-108">Im folgenden Beispiel wird gezeigt, wie verzögertes Laden durch Festlegen von <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> auf `false` ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="3b5cc-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3b5cc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b5cc-109">See also</span></span>

- [<span data-ttu-id="3b5cc-110">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="3b5cc-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="3b5cc-111">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="3b5cc-111">Querying the Database</span></span>](querying-the-database.md)
