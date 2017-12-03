---
title: Analytische Ablaufverfolgung per ETW
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42683acdfe2e63d59a13496b210f83fb97c02de7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="68148-102">Analytische Ablaufverfolgung per ETW</span><span class="sxs-lookup"><span data-stu-id="68148-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="68148-103">Mit der analytischen Ablaufverfolgung von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] können Sie die Diagnoseinformationen während der Ausführung eines [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Diensts erfassen.</span><span class="sxs-lookup"><span data-stu-id="68148-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="68148-104">Die Ereignisse der analytischen Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] werden im [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Stapel an wichtigen Punkten ausgegeben, um in einer Produktionsumgebung die Problembehandlung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Diensten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="68148-104">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="68148-105">Analytische Ablaufverfolgung für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Dienste hat minimale Auswirkungen auf die Leistung eines produktservers, der als Host [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] -Diensten wie diese Ereignisse sehr effizient in eine Sitzung für Event Tracing for Windows (ETW) ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68148-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68148-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68148-106">In This Section</span></span>  
 [<span data-ttu-id="68148-107">Übersicht über die analytische Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="68148-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="68148-108">Erläutert, wie die analytische Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] funktioniert.</span><span class="sxs-lookup"><span data-stu-id="68148-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="68148-109">Dynamisches Aktivieren der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="68148-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="68148-110">Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="68148-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="68148-111">Konfigurieren der Ablaufverfolgung des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="68148-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="68148-112">Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="68148-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="68148-113">Ereignisverweis der analytischen Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="68148-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="68148-114">Zeigt eine Tabelle von Ereignis-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.</span><span class="sxs-lookup"><span data-stu-id="68148-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68148-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68148-115">See Also</span></span>  
 [<span data-ttu-id="68148-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="68148-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="68148-117">Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows</span><span class="sxs-lookup"><span data-stu-id="68148-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
