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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df0f983d646ea89eeef338b9742843e9fa50487b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="1c7fa-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="1c7fa-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="1c7fa-103">Fehler beim Versuch, eine gepoolte Verbindung erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c7fa-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="1c7fa-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="1c7fa-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c7fa-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c7fa-105">Description</span></span>  
 <span data-ttu-id="1c7fa-106">Diese Informationsablaufverfolgung gibt an, dass während des Versuchs, eine zusammengeführte Verbindung wiederzuverwenden, ein Fehler aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="1c7fa-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="1c7fa-107">Dies kann geschehen, weil die zusammengeführte Verbindung nicht kompatibel, nicht bereit oder noch immer aktiv war.</span><span class="sxs-lookup"><span data-stu-id="1c7fa-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="1c7fa-108">Weitere Versuche, andere zusammengeführte Verbindungen wiederzuverwenden werden innerhalb des gegebenen Timeout unternommen, und eine neue Verbindung wird für den Fall erstellt, dass keine verwendbaren Verbindungen gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="1c7fa-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7fa-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c7fa-109">See Also</span></span>  
 [<span data-ttu-id="1c7fa-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="1c7fa-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1c7fa-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="1c7fa-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1c7fa-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="1c7fa-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
