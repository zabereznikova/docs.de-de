---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 97f22a01df84c39915f74fa7677e5dd18154b952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256221"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="85286-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="85286-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>

<span data-ttu-id="85286-103">Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="85286-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="85286-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85286-104">Description</span></span>  

 <span data-ttu-id="85286-105">Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85286-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="85286-106">In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="85286-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="85286-107">Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war.</span><span class="sxs-lookup"><span data-stu-id="85286-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="85286-108">Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="85286-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85286-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85286-109">See also</span></span>

- [<span data-ttu-id="85286-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="85286-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="85286-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="85286-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="85286-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="85286-112">Administration and Diagnostics</span></span>](../index.md)
