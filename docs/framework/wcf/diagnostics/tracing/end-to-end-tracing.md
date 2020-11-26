---
title: End-to-End-Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: a8c06b9e4f70321e6ef3756863390dc62c659557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243949"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="44e98-102">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="44e98-102">End-to-End Tracing</span></span>

<span data-ttu-id="44e98-103">Die End-to-End-Ablauf Verfolgung (E2E) ermöglicht Entwicklern die Ausführung von Code in der Windows Communication Foundation (WCF)-Infrastruktur, um zu ermitteln, warum ein Codepfad fehlgeschlagen ist, oder um eine ausführliche Ablauf Verfolgung für die Kapazitätsplanung und Leistungsanalyse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="44e98-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="44e98-104">Windows Communication Foundation (WCF) bietet drei Korrelations Mechanismen, um die Ursache eines Fehlers zu diagnostizieren: Aktivitäten, Übertragungen und Weitergabe.</span><span class="sxs-lookup"><span data-stu-id="44e98-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="44e98-105">Unter [End-to-End-Ablauf Verfolgungs Szenarien](end-to-end-tracing-scenarios.md) finden Sie eine Liste von End-to-End-Ablauf Verfolgungs Szenarios sowie die entsprechenden Aktivitäten und Ablauf Verfolgungs Entwürfe.</span><span class="sxs-lookup"><span data-stu-id="44e98-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44e98-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="44e98-106">In This Section</span></span>  

 <span data-ttu-id="44e98-107">[Aktivität](activity.md): Beschreibt Aktivitäts Ablauf Verfolgungen im Windows Communication Foundation (WCF)-Ablauf Verfolgungs Modell.</span><span class="sxs-lookup"><span data-stu-id="44e98-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="44e98-108">[Transfer](transfer.md): Beschreibt die Übertragung im Windows Communication Foundation (WCF)-Ablauf Verfolgungs Modell und die Verwendung von Transfer zum Korrelieren von Aktivitäten innerhalb von Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="44e98-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="44e98-109">[Propagierung](propagation.md): Beschreibt die Aktivitäts Weitergabe im Windows Communication Foundation (WCF)-Ablauf Verfolgungs Modell und die Verwendung der Propagierung zum Korrelieren von Aktivitäten über Endpunkte hinweg.</span><span class="sxs-lookup"><span data-stu-id="44e98-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="44e98-110">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="44e98-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="44e98-111">Bietet eine Zusammenfassung aller Aktivitätsablaufverfolgungstypen.</span><span class="sxs-lookup"><span data-stu-id="44e98-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e98-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44e98-112">See also</span></span>

- [<span data-ttu-id="44e98-113">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="44e98-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="44e98-114">Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="44e98-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="44e98-115">End-to-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="44e98-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="44e98-116">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="44e98-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
