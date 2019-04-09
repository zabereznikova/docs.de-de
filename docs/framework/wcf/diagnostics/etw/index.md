---
title: Analytische Ablaufverfolgung per ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193714"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="f5dc7-102">Analytische Ablaufverfolgung per ETW</span><span class="sxs-lookup"><span data-stu-id="f5dc7-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="f5dc7-103">Analytische Ablaufverfolgung von Windows Communication Foundation (WCF) bietet eine Möglichkeit zum Erfassen von Diagnoseinformationen während der Ausführung eines WCF-Diensts.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="f5dc7-104">Analytische Ablaufverfolgung von WCF-Ereignisse werden an wichtigen Punkten im WCF-Stapel zum ermöglichen der Behebung von WCF-Dienste in einer produktionsumgebung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="f5dc7-105">Analytische Ablaufverfolgung für WCF-Dienste hat nur minimale Auswirkungen auf die Leistung eines produktservers, der als Host [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF-Dienste wie diese Ereignisse sehr effizient in eine Sitzung für Event Tracing for Windows (ETW) ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5dc7-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f5dc7-106">In This Section</span></span>  
 [<span data-ttu-id="f5dc7-107">Übersicht über die analytische Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f5dc7-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="f5dc7-108">Erläutert, wie die analytische Ablaufverfolgung von WCF in funktioniert [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5dc7-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="f5dc7-109">Dynamisches Aktivieren der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f5dc7-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="f5dc7-110">Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="f5dc7-111">Konfigurieren der Ablaufverfolgung des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="f5dc7-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="f5dc7-112">Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="f5dc7-113">Ereignisverweis der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f5dc7-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="f5dc7-114">Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.</span><span class="sxs-lookup"><span data-stu-id="f5dc7-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5dc7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5dc7-115">See also</span></span>

- [<span data-ttu-id="f5dc7-116">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="f5dc7-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="f5dc7-117">Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows</span><span class="sxs-lookup"><span data-stu-id="f5dc7-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
