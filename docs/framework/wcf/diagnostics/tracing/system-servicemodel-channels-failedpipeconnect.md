---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: e30b0dd8e18dcba4a4c15aab6cf5f321492eb1a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476924"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="185c0-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="185c0-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="185c0-103">Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="185c0-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="185c0-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="185c0-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="185c0-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="185c0-105">Description</span></span>  
 <span data-ttu-id="185c0-106">Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="185c0-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="185c0-107">Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="185c0-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="185c0-108">Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="185c0-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185c0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="185c0-109">See Also</span></span>  
 [<span data-ttu-id="185c0-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="185c0-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="185c0-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="185c0-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="185c0-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="185c0-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
