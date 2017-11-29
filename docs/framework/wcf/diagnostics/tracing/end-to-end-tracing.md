---
title: End-to-End-Ablaufverfolgung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b4cdbc12f57c733d8e8ba3753ce5a2f29ab28ffd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="eefac-102">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="eefac-102">End-to-End Tracing</span></span>
<span data-ttu-id="eefac-103">Die End-to-End (e2e)-Ablaufverfolgung ermöglicht Entwicklern das Nachverfolgen der Ausführung von Code in der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Infrastruktur, um zu ermitteln, warum bei einem Codepfad ein Fehler aufgetreten ist, oder um eine ausführliche Ablaufverfolgung zur Kapazitätsplanung und Leistungsanalyse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eefac-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="eefac-104"> verfügt über drei Korrelationsmechanismen zum Ermitteln von Fehlerursachen: Aktivitäten, Übertragungen und Weitergabe.</span><span class="sxs-lookup"><span data-stu-id="eefac-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="eefac-105">Finden Sie unter [End-To-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) eine Liste der End-to-End-ablaufverfolgungsszenarien und ihre entsprechenden Aktivität und Entwurf tracing.</span><span class="sxs-lookup"><span data-stu-id="eefac-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eefac-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eefac-106">In This Section</span></span>  
 <span data-ttu-id="eefac-107">[Aktivität](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): aktivitätsablaufverfolgungen im beschreibt die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] aktivitätsablaufverfolgungs-Modell.</span><span class="sxs-lookup"><span data-stu-id="eefac-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="eefac-108">[Übertragung](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): Beschreibt die Übertragung in die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing Modell und Übertragung zum Korrelieren von Aktivitäten innerhalb von Endpunkten verwenden.</span><span class="sxs-lookup"><span data-stu-id="eefac-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="eefac-109">[Weitergabe](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): Aktivitätsweitergabe im beschreibt die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing Modell, und Verwenden der Weitergabe zur Korrelation von Aktivitäten über Endpunkte hinweg.</span><span class="sxs-lookup"><span data-stu-id="eefac-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="eefac-110">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="eefac-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="eefac-111">Bietet eine Zusammenfassung aller Aktivitätsablaufverfolgungstypen.</span><span class="sxs-lookup"><span data-stu-id="eefac-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefac-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eefac-112">See Also</span></span>  
 [<span data-ttu-id="eefac-113">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="eefac-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="eefac-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="eefac-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="eefac-115">End-To-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="eefac-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="eefac-116">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="eefac-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
