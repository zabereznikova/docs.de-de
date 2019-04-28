---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: de0bdd9e5ab922b09249bf550fde745042be8e58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666754"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="500da-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="500da-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="500da-103">Fehler beim Versuch, eine gepoolte Verbindung erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="500da-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="500da-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="500da-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="500da-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="500da-105">Description</span></span>  
 <span data-ttu-id="500da-106">Diese Informationsablaufverfolgung gibt an, dass während des Versuchs, eine zusammengeführte Verbindung wiederzuverwenden, ein Fehler aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="500da-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="500da-107">Dies kann geschehen, weil die zusammengeführte Verbindung nicht kompatibel, nicht bereit oder noch immer aktiv war.</span><span class="sxs-lookup"><span data-stu-id="500da-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="500da-108">Weitere Versuche, andere zusammengeführte Verbindungen wiederzuverwenden werden innerhalb des gegebenen Timeout unternommen, und eine neue Verbindung wird für den Fall erstellt, dass keine verwendbaren Verbindungen gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="500da-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="500da-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="500da-109">See also</span></span>

- [<span data-ttu-id="500da-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="500da-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="500da-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="500da-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="500da-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="500da-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
