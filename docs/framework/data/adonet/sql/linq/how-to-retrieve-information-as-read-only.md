---
title: 'Vorgehensweise: Abrufen von Informationen als schreibgeschützt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: b98c5e6ea49695015eb566ca2176b23c5260017a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928710"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="e1895-102">Vorgehensweise: Abrufen von Informationen als schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e1895-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="e1895-103">Wenn Sie nicht beabsichtigen, die Daten zu ändern, können Sie die Abfrageleistung steigern, indem Sie schreibgeschützte Ergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1895-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="e1895-104">Sie implementieren die schreibgeschützte Verarbeitung, indem Sie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="e1895-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1895-105">Wird <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festgelegt, wird <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> implizit auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e1895-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1895-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1895-106">Example</span></span>  
 <span data-ttu-id="e1895-107">Im folgenden Code wird eine schreibgeschützte Auflistung von Mitarbeitereinstellungsdaten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e1895-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e1895-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1895-108">See also</span></span>

- [<span data-ttu-id="e1895-109">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="e1895-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="e1895-110">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="e1895-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="e1895-111">Verzögertes im Vergleich zu unmittelbarem Laden</span><span class="sxs-lookup"><span data-stu-id="e1895-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
