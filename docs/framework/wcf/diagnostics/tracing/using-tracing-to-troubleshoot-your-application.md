---
title: Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb46ad5fe95405c78baf3173a982969e0e7092fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="a1a4e-102">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="a1a4e-102">Using Tracing to Troubleshoot Your Application</span></span>
<span data-ttu-id="a1a4e-103">Dieser Abschnitt enthält verschiedene Themen, in denen beschrieben wird, wie Sie Anwendungsfehler mit der Ablaufverfolgung beheben.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1a4e-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1a4e-104">In This Section</span></span>  
 [<span data-ttu-id="a1a4e-105">Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="a1a4e-105">Recommended Settings for Tracing and Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="a1a4e-106">Beschreibt vorgeschlagene Einstellungen für Produktions- und Debugumgebungen.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="a1a4e-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="a1a4e-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="a1a4e-108">Beschreibt, wie Sie mit dem Service Trace Viewer-Tool Ablaufverfolgungsdaten anzeigen, korrelieren und analysieren können.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="a1a4e-109">Bedeutende Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="a1a4e-109">Significant Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/significant-traces.md)  
 <span data-ttu-id="a1a4e-110">Eine Liste der wichtigsten Ablaufverfolgungen, die von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-110">A list of major traces emitted by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="a1a4e-111">Debuggen auf dem Client</span><span class="sxs-lookup"><span data-stu-id="a1a4e-111">Debugging on the Client</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/debugging-on-the-client.md)  
 <span data-ttu-id="a1a4e-112">Ermöglicht Clients, die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="a1a4e-113">End-to-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="a1a4e-113">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="a1a4e-114">Beschreibt für E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Szenarien verwendete Ablaufverfolgungen, z.&#160;B. synchrone wsHttp-Anforderungsantworten und asynchrone unidirektionale TCP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-114">Describes traces used for E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="a1a4e-115">Ausgeben von Benutzercode-Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="a1a4e-115">Emitting User-Code Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)  
 <span data-ttu-id="a1a4e-116">Beschreibt die programmgesteuerte Ausgabe von Ablaufverfolgungen in Benutzercode, sodass Sie proaktiv Instrumentierungsdaten erstellen können, die später zur Diagnose und in Korrelation mit WCF-Ablaufverfolgungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1a4e-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a4e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1a4e-117">See Also</span></span>  
 [<span data-ttu-id="a1a4e-118">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="a1a4e-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="a1a4e-119">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a1a4e-119">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a1a4e-120">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="a1a4e-120">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
