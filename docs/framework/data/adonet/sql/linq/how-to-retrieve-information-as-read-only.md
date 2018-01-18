---
title: "Gewusst wie: Abrufen von Informationen als schreibgeschützt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7144863e43ec816ad2359c6c48f6d38babb3b46
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="6736a-102">Gewusst wie: Abrufen von Informationen als schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6736a-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="6736a-103">Wenn Sie nicht beabsichtigen, die Daten zu ändern, können Sie die Abfrageleistung steigern, indem Sie schreibgeschützte Ergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="6736a-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="6736a-104">Sie implementieren die schreibgeschützte Verarbeitung, indem Sie <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="6736a-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6736a-105">Wird <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> auf `false` festgelegt, wird <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> implizit auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6736a-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6736a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6736a-106">Example</span></span>  
 <span data-ttu-id="6736a-107">Im folgenden Code wird eine schreibgeschützte Auflistung von Mitarbeitereinstellungsdaten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6736a-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6736a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6736a-108">See Also</span></span>  
 [<span data-ttu-id="6736a-109">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="6736a-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="6736a-110">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6736a-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [<span data-ttu-id="6736a-111">Verzögertes im Vergleich zu unmittelbarem Laden</span><span class="sxs-lookup"><span data-stu-id="6736a-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
