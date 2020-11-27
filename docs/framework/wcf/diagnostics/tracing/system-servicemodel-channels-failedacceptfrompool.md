---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 8615cca7d4ed8ea1f40baa9502e7136d4349eb9c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256312"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="461c1-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="461c1-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>

<span data-ttu-id="461c1-103">Fehler beim Versuch, eine gepoolte Verbindung erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="461c1-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="461c1-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="461c1-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="461c1-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="461c1-105">Description</span></span>  

 <span data-ttu-id="461c1-106">Diese Informationsablaufverfolgung gibt an, dass während des Versuchs, eine zusammengeführte Verbindung wiederzuverwenden, ein Fehler aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="461c1-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="461c1-107">Dies kann geschehen, weil die zusammengeführte Verbindung nicht kompatibel, nicht bereit oder noch immer aktiv war.</span><span class="sxs-lookup"><span data-stu-id="461c1-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="461c1-108">Weitere Versuche, andere zusammengeführte Verbindungen wiederzuverwenden werden innerhalb des gegebenen Timeout unternommen, und eine neue Verbindung wird für den Fall erstellt, dass keine verwendbaren Verbindungen gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="461c1-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461c1-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="461c1-109">See also</span></span>

- [<span data-ttu-id="461c1-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="461c1-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="461c1-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="461c1-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="461c1-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="461c1-112">Administration and Diagnostics</span></span>](../index.md)
