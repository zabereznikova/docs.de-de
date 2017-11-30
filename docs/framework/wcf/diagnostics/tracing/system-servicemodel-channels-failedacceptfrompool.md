---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e50e104816567927f53673f9b1da9c3c5beac3d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="305de-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="305de-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="305de-103">Fehler beim Versuch, eine gepoolte Verbindung erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="305de-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="305de-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="305de-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="305de-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="305de-105">Description</span></span>  
 <span data-ttu-id="305de-106">Diese Informationsablaufverfolgung gibt an, dass während des Versuchs, eine zusammengeführte Verbindung wiederzuverwenden, ein Fehler aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="305de-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="305de-107">Dies kann geschehen, weil die zusammengeführte Verbindung nicht kompatibel, nicht bereit oder noch immer aktiv war.</span><span class="sxs-lookup"><span data-stu-id="305de-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="305de-108">Weitere Versuche, andere zusammengeführte Verbindungen wiederzuverwenden werden innerhalb des gegebenen Timeout unternommen, und eine neue Verbindung wird für den Fall erstellt, dass keine verwendbaren Verbindungen gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="305de-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305de-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="305de-109">See Also</span></span>  
 [<span data-ttu-id="305de-110">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="305de-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="305de-111">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="305de-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="305de-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="305de-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
