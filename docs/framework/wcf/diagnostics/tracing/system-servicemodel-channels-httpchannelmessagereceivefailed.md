---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: e11b376924ee74e5d0d67da0cac59af41655dc44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594074"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="b812b-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="b812b-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="b812b-103">Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="b812b-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b812b-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b812b-104">Description</span></span>  
 <span data-ttu-id="b812b-105">Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b812b-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="b812b-106">In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b812b-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="b812b-107">Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war.</span><span class="sxs-lookup"><span data-stu-id="b812b-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="b812b-108">Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b812b-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b812b-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b812b-109">See also</span></span>

- [<span data-ttu-id="b812b-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b812b-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="b812b-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="b812b-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b812b-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="b812b-112">Administration and Diagnostics</span></span>](../index.md)
