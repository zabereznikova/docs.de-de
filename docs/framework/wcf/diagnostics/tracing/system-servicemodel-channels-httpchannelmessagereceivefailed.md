---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1bbad8d743ff64aea923e7fbf62871e495253aea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="e4c2a-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="e4c2a-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="e4c2a-103">Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="e4c2a-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e4c2a-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4c2a-104">Description</span></span>  
 <span data-ttu-id="e4c2a-105">Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e4c2a-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="e4c2a-106">In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="e4c2a-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="e4c2a-107">Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war.</span><span class="sxs-lookup"><span data-stu-id="e4c2a-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="e4c2a-108">Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="e4c2a-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c2a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4c2a-109">See Also</span></span>  
 [<span data-ttu-id="e4c2a-110">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e4c2a-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e4c2a-111">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="e4c2a-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="e4c2a-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="e4c2a-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
