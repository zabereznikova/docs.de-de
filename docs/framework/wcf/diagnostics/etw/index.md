---
title: Analytische Ablaufverfolgung per ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798090"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="da022-102">Analytische Ablaufverfolgung per ETW</span><span class="sxs-lookup"><span data-stu-id="da022-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="da022-103">Die analytische Ablauf Verfolgung von Windows Communication Foundation (WCF) bietet eine Möglichkeit zum Erfassen von Diagnoseinformationen während der Ausführung eines WCF-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="da022-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="da022-104">WCF-analytische Ablauf Verfolgungs Ereignisse werden an wichtigen Punkten im WCF-Stapel ausgegeben, um die Problembehandlung von WCF-Diensten in einer Produktionsumgebung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="da022-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="da022-105">Die analytische Ablauf Verfolgung für WCF-Dienste wirkt sich nur minimal auf die Leistung eines Produkt [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] Servers aus, der WCF-Dienste hostet, da diese Ereignisse sehr effizient an eine Ereignis Ablauf Verfolgung für Windows (ETW)-Sitzung ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da022-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da022-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da022-106">In This Section</span></span>  
 [<span data-ttu-id="da022-107">Übersicht über die analytische Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="da022-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="da022-108">Erläutert, wie die analytische WCF- [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]Ablauf Verfolgung in funktioniert.</span><span class="sxs-lookup"><span data-stu-id="da022-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="da022-109">Dynamisches Aktivieren der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="da022-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="da022-110">Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="da022-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="da022-111">Konfigurieren der Ablaufverfolgung des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="da022-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="da022-112">Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="da022-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="da022-113">Ereignisreferenz der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="da022-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="da022-114">Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.</span><span class="sxs-lookup"><span data-stu-id="da022-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da022-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da022-115">See also</span></span>

- [<span data-ttu-id="da022-116">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="da022-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="da022-117">Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows</span><span class="sxs-lookup"><span data-stu-id="da022-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
