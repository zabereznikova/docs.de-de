---
title: End-to-End-Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fd2964b39c758e41620fb453ddd8f61a1aa550aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092119"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="2edbc-102">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2edbc-102">End-to-End Tracing</span></span>
<span data-ttu-id="2edbc-103">End-to-End kann (e2e) Ablaufverfolgung die Entwickler befolgen die Ausführung von Code in der Windows Communication Foundation (WCF)-Infrastruktur zu untersuchen, warum ein Codepfad ein Fehler aufgetreten ist oder ausführliche Ablaufverfolgung zur Analyse der Kapazität und Leistungsanalyse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2edbc-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="2edbc-104">Windows Communication Foundation (WCF) verfügt über drei korrelationsmechanismen zum Diagnostizieren der Ursache des Fehlers: Aktivitäten, Übertragungen und Weitergabe.</span><span class="sxs-lookup"><span data-stu-id="2edbc-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="2edbc-105">Finden Sie unter [End-To-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) eine Liste der End-to-End-ablaufverfolgungsszenarien und deren entsprechende Aktivität und den ablaufverfolgungsentwurf.</span><span class="sxs-lookup"><span data-stu-id="2edbc-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2edbc-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2edbc-106">In This Section</span></span>  
 <span data-ttu-id="2edbc-107">[Aktivität](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Beschreibt aktivitätsablaufverfolgungen im ablaufverfolgungsmodell Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2edbc-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="2edbc-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Beschreibt die Übertragung in die Windows Communication Foundation (WCF)-aktivitätsablaufverfolgungs-Modell und Übertragung zum Korrelieren von Aktivitäten innerhalb von Endpunkten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2edbc-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="2edbc-109">[Weitergabe](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Beschreibt die Aktivitätsweitergabe in Windows Communication Foundation (WCF)-ablaufverfolgungsmodell sowie die Verwendung der Weitergabe zum endpunktübergreifenden Korrelieren von Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="2edbc-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="2edbc-110">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="2edbc-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="2edbc-111">Bietet eine Zusammenfassung aller Aktivitätsablaufverfolgungstypen.</span><span class="sxs-lookup"><span data-stu-id="2edbc-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edbc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2edbc-112">See also</span></span>

- [<span data-ttu-id="2edbc-113">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2edbc-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="2edbc-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="2edbc-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="2edbc-115">End-to-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="2edbc-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="2edbc-116">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="2edbc-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
