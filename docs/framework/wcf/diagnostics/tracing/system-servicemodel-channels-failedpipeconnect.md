---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: b3b34b2f4ab2987360030d614c8e65cd878d4d14
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256247"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="904a8-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="904a8-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>

<span data-ttu-id="904a8-103">Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="904a8-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="904a8-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="904a8-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="904a8-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="904a8-105">Description</span></span>  

 <span data-ttu-id="904a8-106">Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="904a8-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="904a8-107">Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="904a8-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="904a8-108">Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="904a8-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904a8-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="904a8-109">See also</span></span>

- [<span data-ttu-id="904a8-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="904a8-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="904a8-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="904a8-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="904a8-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="904a8-112">Administration and Diagnostics</span></span>](../index.md)
