---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: b848963caff706ff8a886c1e358ad6688e9611c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666689"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="56567-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="56567-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="56567-103">Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="56567-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="56567-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56567-104">Description</span></span>  
 <span data-ttu-id="56567-105">Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="56567-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="56567-106">In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="56567-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="56567-107">Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war.</span><span class="sxs-lookup"><span data-stu-id="56567-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="56567-108">Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="56567-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56567-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56567-109">See also</span></span>

- [<span data-ttu-id="56567-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="56567-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="56567-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="56567-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="56567-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="56567-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
