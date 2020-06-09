---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 790a15e5401850f2767cb06f5f321ad80c674f2b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84582412"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="57dc1-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="57dc1-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="57dc1-103">Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="57dc1-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="57dc1-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="57dc1-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="57dc1-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57dc1-105">Description</span></span>  
 <span data-ttu-id="57dc1-106">Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="57dc1-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="57dc1-107">Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="57dc1-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="57dc1-108">Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="57dc1-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57dc1-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57dc1-109">See also</span></span>

- [<span data-ttu-id="57dc1-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="57dc1-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="57dc1-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="57dc1-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="57dc1-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="57dc1-112">Administration and Diagnostics</span></span>](../index.md)
