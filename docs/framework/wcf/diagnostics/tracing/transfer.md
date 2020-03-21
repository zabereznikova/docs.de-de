---
title: Übertragung
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: e0ebfff97cd33e7a588a1ab92399a97a0fbec039
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185707"
---
# <a name="transfer"></a><span data-ttu-id="27de4-102">Übertragung</span><span class="sxs-lookup"><span data-stu-id="27de4-102">Transfer</span></span>
<span data-ttu-id="27de4-103">In diesem Thema wird die Übertragung im WCF-Aktivitätsablaufverfolgungsmodell (Windows Communication Foundation) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="27de4-103">This topic describes transfer in the Windows Communication Foundation (WCF) activity tracing model.</span></span>  
  
## <a name="transfer-definition"></a><span data-ttu-id="27de4-104">Übertragungsdefinition</span><span class="sxs-lookup"><span data-stu-id="27de4-104">Transfer Definition</span></span>  
 <span data-ttu-id="27de4-105">Übertragungen zwischen Aktivitäten stellen einen kausalen Zusammenhang zwischen Ereignissen in den zugehörigen Aktivitäten innerhalb von Endpunkten dar.</span><span class="sxs-lookup"><span data-stu-id="27de4-105">Transfers between activities represent causal relationships between events in the related activities within endpoints.</span></span> <span data-ttu-id="27de4-106">Zwei Aktivitäten stehen mit Übertragungen in Beziehung, wenn eine Ablaufsteuerung zwischen den Aktivitäten besteht, z. B. ein Methodenaufruf, der Aktivitätsgrenzen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="27de4-106">Two activities are related with transfers when control flows between these activities, for example, a method call crossing activity boundaries.</span></span> <span data-ttu-id="27de4-107">Wenn in WCF Bytes im Dienst eingehen, wird die Aktivität "Hören bei" an die Aktivität Bytes empfangen übertragen, in der das Nachrichtenobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="27de4-107">In WCF, when bytes are incoming on the service, the Listen At activity is transferred to the Receive Bytes activity where the message object is created.</span></span> <span data-ttu-id="27de4-108">Eine Liste der End-to-End-Ablaufverfolgungsszenarien sowie des jeweiligen Aktivitäts- und Ablaufverfolgungsentwurfs finden Sie unter [End-to-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="27de4-108">For a list of end-to-end tracing scenarios, and their respective activity and tracing design, see [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span></span>  
  
 <span data-ttu-id="27de4-109">Um Übertragungsablaufverfolgungen auszugeben, verwenden Sie die `ActivityTracing`-Einstellung auf der Ablaufverfolgungsquelle, wie im folgenden Konfigurationscode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="27de4-109">To emit transfer traces, use the `ActivityTracing` setting on the trace source as demonstrated by the following configuration code.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a><span data-ttu-id="27de4-110">Verwenden der Übertragung zur Korrelation von Aktivitäten innerhalb von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="27de4-110">Using Transfer to Correlate Activities Within Endpoints</span></span>  
 <span data-ttu-id="27de4-111">Aktivitäten und Übertragungen ermöglichen es dem Benutzer, die Ursache eines Fehlers nach Wahrscheinlichkeit zu lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="27de4-111">Activities and transfers permit the user to probabilistically locate the root cause of an error.</span></span> <span data-ttu-id="27de4-112">Übertragen wir beispielsweise vor und zurück zwischen Aktivität M und N in den Komponenten M und N und tritt nach Rückübertragung zu M auf N ein Absturz auf, können wir zu dem Schluss kommen, dass der Grund hierfür wahrscheinlich an der Datenrückübertragung von N zu M liegt.</span><span class="sxs-lookup"><span data-stu-id="27de4-112">For example, if we transfer back and forth between activities M and N respectively in components M and N, and a crash happens in N right after the transfer back to M, we can draw the conclusion that it is likely due to N’s passing data back to M.</span></span>  
  
 <span data-ttu-id="27de4-113">Eine Übertragungsablaufverfolgung wird von Aktivität M an Aktivität N ausgegeben, wenn ein Steuerungsfluss zwischen M und N besteht. Beispielsweise führt N aufgrund eines Methodenaufrufs über die Aktivitätsgrenzen hinweg Arbeit für M aus.</span><span class="sxs-lookup"><span data-stu-id="27de4-113">A transfer trace is emitted from activity M to activity N when there is a flow of control between M and N. For example, N performs some work for M because of a method call crossing the activities’ boundaries.</span></span> <span data-ttu-id="27de4-114">N ist möglicherweise bereits vorhanden oder wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="27de4-114">N may already exist or has been created.</span></span> <span data-ttu-id="27de4-115">N wird von M erzeugt, wenn N eine neue Aktivität ist, die Arbeit für M ausführt.</span><span class="sxs-lookup"><span data-stu-id="27de4-115">N is spawned by M when N is a new activity that performs some work for M.</span></span>  
  
 <span data-ttu-id="27de4-116">Nach der Übertragung von M zu N erfolgt möglicherweise keine Rückübertragung von N zu M. Dies liegt daran, dass M Arbeit in N erstellen kann und nicht nachverfolgt, wann N die Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="27de4-116">A transfer from M to N may not be followed by a transfer back from N to M. This is because M can spawn some work in N and do not track when N completes that work.</span></span> <span data-ttu-id="27de4-117">In der Tat kann M beendet werden, bevor N seine Aufgabe ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="27de4-117">In fact, M can terminate before N completes its task.</span></span> <span data-ttu-id="27de4-118">Dies geschieht in der Aktivität "Open ServiceHost" (M), die Listener-Aktivitäten (N) erzeugt und dann beendet wird.</span><span class="sxs-lookup"><span data-stu-id="27de4-118">This happens in the "Open ServiceHost" activity (M) that spawns Listener activities (N) and then terminates.</span></span> <span data-ttu-id="27de4-119">Eine Rückübertragung von N zu M bedeutet, dass N die zu M gehörende Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="27de4-119">A transfer back from N to M means that N completed the work related to M.</span></span>  
  
 <span data-ttu-id="27de4-120">N kann mit der Durchführung anderer zu M gehörender Verarbeitungen fortfahren, beispielsweise eine bestehende Authentifikatoraktivität (N), die weiterhin Anmeldeanforderungen (M) von unterschiedlichen Anmeldeaktivitäten erhält.</span><span class="sxs-lookup"><span data-stu-id="27de4-120">N can continue performing other processing unrelated to M, for example, an existing authenticator activity (N) that keeps receiving login requests (M) from different login activities.</span></span>  
  
 <span data-ttu-id="27de4-121">Zwischen den Aktivitäten M und N besteht nicht zwingend eine Schachtelungsbeziehung. Dies kann aus zwei Gründen der Fall sein.</span><span class="sxs-lookup"><span data-stu-id="27de4-121">A nesting relationship does not necessarily exist between activities M and N. This can happen due to two reasons.</span></span> <span data-ttu-id="27de4-122">Der erste Grund ist, wenn Aktivität M die in N durchgeführte Verarbeitung nicht überwacht, obwohl M Initiator von N ist. Der zweite Grund kann darin liegen, dass N bereits besteht.</span><span class="sxs-lookup"><span data-stu-id="27de4-122">First, when activity M does not monitor the actual processing performed in N although M initiated N. Second, when N already exists.</span></span>  
  
## <a name="example-of-transfers"></a><span data-ttu-id="27de4-123">Beispiel für Übertragungen</span><span class="sxs-lookup"><span data-stu-id="27de4-123">Example of Transfers</span></span>  
 <span data-ttu-id="27de4-124">Im Folgenden werden zwei Übertragungsbeispiele aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="27de4-124">The following lists two transfer examples.</span></span>  
  
- <span data-ttu-id="27de4-125">Bei der Erstellung eines Diensthosts erhält der Konstruktor Steuerung über den Aufrufcode, oder der Aufrufcode überträgt zum Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="27de4-125">When you create a service host, the constructor gains control from the calling code, or the calling code transfers to the constructor.</span></span> <span data-ttu-id="27de4-126">Wenn der Konstruktor die Ausführung beendet hat, gibt er die Steuerung zum aufrufenden Code zurück oder der Konstruktor überträgt zum aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="27de4-126">When the constructor has finished executing, it returns control to the calling code, or the constructor transfers back to the calling code.</span></span> <span data-ttu-id="27de4-127">Dies ist der Fall bei einer geschachtelten Beziehung.</span><span class="sxs-lookup"><span data-stu-id="27de4-127">This is the case of a nested relationship.</span></span>  
  
- <span data-ttu-id="27de4-128">Wenn ein Listener mit der Verarbeitung von Transportdaten beginnt, erstellt er einen neuen Thread und übergibt den geeigneten Kontext für die Verarbeitung, d. h. die Steuerung und die Daten, an die Bytes empfangen-Aktivität weiter.</span><span class="sxs-lookup"><span data-stu-id="27de4-128">When a listener starts processing transport data, it creates a new thread and hands to the Receive Bytes activity the appropriate context for processing, passing control and data.</span></span> <span data-ttu-id="27de4-129">Hat dieser Thread die Verarbeitung der Anforderung beendet, gibt die Byteempfang-Aktivität keine Informationen zum Listener zurück.</span><span class="sxs-lookup"><span data-stu-id="27de4-129">When that thread has finished processing the request, the Receive Bytes activity passes nothing back to the listener.</span></span> <span data-ttu-id="27de4-130">In diesem Fall haben wir eine Übertragung in die neue Threadaktivität, aber keine heraus.</span><span class="sxs-lookup"><span data-stu-id="27de4-130">In this case, we have a transfer in but no transfer out of the new thread activity.</span></span> <span data-ttu-id="27de4-131">Die beiden Aktivitäten sind verknüpft, aber nicht geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="27de4-131">The two activities are related but not nested.</span></span>  
  
## <a name="activity-transfer-sequence"></a><span data-ttu-id="27de4-132">Aktivitätsübertragungssequenz</span><span class="sxs-lookup"><span data-stu-id="27de4-132">Activity Transfer Sequence</span></span>  
 <span data-ttu-id="27de4-133">Eine gut strukturierte Aktivitätsübertragungssequenz schließt die folgenden Schritte ein.</span><span class="sxs-lookup"><span data-stu-id="27de4-133">A well-formed activity transfer sequence includes the following steps.</span></span>  
  
1. <span data-ttu-id="27de4-134">Starten Sie eine neue Aktivität, die aus der Auswahl einer neuen gAId besteht.</span><span class="sxs-lookup"><span data-stu-id="27de4-134">Begin a new activity, which consists of selecting a new gAId.</span></span>  
  
2. <span data-ttu-id="27de4-135">Geben Sie eine Übertragungsablaufverfolgung zu dieser neuen gAId von der aktuellen Aktivitäts-ID aus.</span><span class="sxs-lookup"><span data-stu-id="27de4-135">Emit a transfer trace to that new gAId from the current activity ID</span></span>  
  
3. <span data-ttu-id="27de4-136">Festlegen der neuen ID in TLS</span><span class="sxs-lookup"><span data-stu-id="27de4-136">Set the new ID in TLS</span></span>  
  
4. <span data-ttu-id="27de4-137">Geben Sie eine Start-Ablaufverfolgung aus, um den Beginn der neuen Aktivität festzulegen.</span><span class="sxs-lookup"><span data-stu-id="27de4-137">Emit a start trace to indicate the beginning of the new activity by.</span></span>  
  
5. <span data-ttu-id="27de4-138">Die Rückgabe zur Originalaktivität besteht aus Folgendem:</span><span class="sxs-lookup"><span data-stu-id="27de4-138">Return to the original activity consists of the following:</span></span>  
  
6. <span data-ttu-id="27de4-139">Ausgabe einer Übertragungsablaufverfolgung zur Original-gAId</span><span class="sxs-lookup"><span data-stu-id="27de4-139">Emit a transfer trace to the original gAId</span></span>  
  
7. <span data-ttu-id="27de4-140">Ausgabe einer Stop-Ablaufverfolgung, um das Ende der neuen Aktivität festzulegen</span><span class="sxs-lookup"><span data-stu-id="27de4-140">Emit a Stop trace to indicate the end of the new activity</span></span>  
  
8. <span data-ttu-id="27de4-141">Festlegen von TLS auf die alte gAId</span><span class="sxs-lookup"><span data-stu-id="27de4-141">Set TLS to the old gAId.</span></span>  
  
 <span data-ttu-id="27de4-142">Das folgende Codebeispiel veranschaulicht, wie Sie dabei vorgehen:</span><span class="sxs-lookup"><span data-stu-id="27de4-142">The following code example demonstrates how to do this.</span></span> <span data-ttu-id="27de4-143">Bei diesem Beispiel wird davon ausgegangen, dass ein Sperraufruf bei der Übertragung zur neuen Aktivität ausgelöst wurde, und es enthält Suspend-/Resume-Ablaufverfolungen.</span><span class="sxs-lookup"><span data-stu-id="27de4-143">This sample assumes a blocking call is made when transferring to the new activity, and includes suspend/resume traces.</span></span>  
  
```csharp
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  

// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();

// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  

// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  

// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  

// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  

// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  

// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);

// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  

// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  

// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;

// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="27de4-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27de4-144">See also</span></span>

- [<span data-ttu-id="27de4-145">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="27de4-145">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="27de4-146">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="27de4-146">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="27de4-147">End-to-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="27de4-147">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="27de4-148">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="27de4-148">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
