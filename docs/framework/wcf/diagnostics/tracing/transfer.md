---
title: Übertragung
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: 4753ec85c458a0dde3db4a6b7cdad41c69185019
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311018"
---
# <a name="transfer"></a>Übertragung
Dieses Thema beschreibt die Übertragung in Windows Communication Foundation (WCF) aktivitätsablaufverfolgungs-Modell.  
  
## <a name="transfer-definition"></a>Übertragungsdefinition  
 Übertragungen zwischen Aktivitäten stellen einen kausalen Zusammenhang zwischen Ereignissen in den zugehörigen Aktivitäten innerhalb von Endpunkten dar. Zwei Aktivitäten stehen mit Übertragungen in Beziehung, wenn eine Ablaufsteuerung zwischen den Aktivitäten besteht, z. B. ein Methodenaufruf, der Aktivitätsgrenzen überschreitet. In WCF Wenn Bytes für den Dienst eingehende sind wird der lauschaktivität an die Byteempfang-Aktivität übertragen, in das Nachrichtenobjekt erstellt wird. Eine Liste der End-to-End-ablaufverfolgungsszenarien und deren entsprechende Aktivität und den ablaufverfolgungsentwurf, finden Sie unter [End-To-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).  
  
 Um Übertragungsablaufverfolgungen auszugeben, verwenden Sie die `ActivityTracing`-Einstellung auf der Ablaufverfolgungsquelle, wie im folgenden Konfigurationscode gezeigt.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a>Verwenden der Übertragung zur Korrelation von Aktivitäten innerhalb von Endpunkten  
 Aktivitäten und Übertragungen ermöglichen es dem Benutzer, die Ursache eines Fehlers nach Wahrscheinlichkeit zu lokalisieren. Übertragen wir beispielsweise vor und zurück zwischen Aktivität M und N in den Komponenten M und N und tritt nach Rückübertragung zu M auf N ein Absturz auf, können wir zu dem Schluss kommen, dass der Grund hierfür wahrscheinlich an der Datenrückübertragung von N zu M liegt.  
  
 Eine Übertragungsablaufverfolgung wird von Aktivität M an Aktivität N ausgegeben, wenn ein Steuerungsfluss zwischen M und N besteht. Beispielsweise führt N aufgrund eines Methodenaufrufs über die Aktivitätsgrenzen hinweg Arbeit für M aus. N ist möglicherweise bereits vorhanden oder wurde erstellt. N wird von M erzeugt, wenn N eine neue Aktivität ist, die Arbeit für M ausführt.  
  
 Nach der Übertragung von M zu N erfolgt möglicherweise keine Rückübertragung von N zu M. Dies liegt daran, dass M Arbeit in N erstellen kann und nicht nachverfolgt, wann N die Arbeit abgeschlossen hat. In der Tat kann M beendet werden, bevor N seine Aufgabe ausgeführt hat. Dies geschieht in der "Open ServiceHost"-Aktivität (M), die listeneraktivitäten (N), und klicken Sie dann beendet. Eine Rückübertragung von N zu M bedeutet, dass N die zu M gehörende Arbeit abgeschlossen hat.  
  
 N kann mit der Durchführung anderer zu M gehörender Verarbeitungen fortfahren, beispielsweise eine bestehende Authentifikatoraktivität (N), die weiterhin Anmeldeanforderungen (M) von unterschiedlichen Anmeldeaktivitäten erhält.  
  
 Zwischen den Aktivitäten M und N besteht nicht zwingend eine Schachtelungsbeziehung. Dies kann aus zwei Gründen der Fall sein. Der erste Grund ist, wenn Aktivität M die in N durchgeführte Verarbeitung nicht überwacht, obwohl M Initiator von N ist. Der zweite Grund kann darin liegen, dass N bereits besteht.  
  
## <a name="example-of-transfers"></a>Beispiel für Übertragungen  
 Im Folgenden werden zwei Übertragungsbeispiele aufgelistet.  
  
-   Bei der Erstellung eines Diensthosts erhält der Konstruktor Steuerung über den Aufrufcode, oder der Aufrufcode überträgt zum Konstruktor. Wenn der Konstruktor die Ausführung beendet hat, gibt er die Steuerung zum aufrufenden Code zurück oder der Konstruktor überträgt zum aufrufenden Code zurück. Dies ist der Fall bei einer geschachtelten Beziehung.  
  
-   Wenn ein Listener mit der Verarbeitung von Transportdaten beginnt, erstellt er einen neuen Thread und übergibt den geeigneten Kontext für die Verarbeitung, d. h. die Steuerung und die Daten, an die Bytes empfangen-Aktivität weiter. Hat dieser Thread die Verarbeitung der Anforderung beendet, gibt die Byteempfang-Aktivität keine Informationen zum Listener zurück. In diesem Fall haben wir eine Übertragung in die neue Threadaktivität, aber keine heraus. Die beiden Aktivitäten sind verknüpft, aber nicht geschachtelt.  
  
## <a name="activity-transfer-sequence"></a>Aktivitätsübertragungssequenz  
 Eine gut strukturierte Aktivitätsübertragungssequenz schließt die folgenden Schritte ein.  
  
1. Starten Sie eine neue Aktivität, die aus der Auswahl einer neuen gAId besteht.  
  
2. Geben Sie eine Übertragungsablaufverfolgung zu dieser neuen gAId von der aktuellen Aktivitäts-ID aus.  
  
3. Festlegen der neuen ID in TLS  
  
4. Geben Sie eine Start-Ablaufverfolgung aus, um den Beginn der neuen Aktivität festzulegen.  
  
5. Die Rückgabe zur Originalaktivität besteht aus Folgendem:  
  
6. Ausgabe einer Übertragungsablaufverfolgung zur Original-gAId  
  
7. Ausgabe einer Stop-Ablaufverfolgung, um das Ende der neuen Aktivität festzulegen  
  
8. Festlegen von TLS auf die alte gAId  
  
 Das folgende Codebeispiel veranschaulicht, wie Sie dabei vorgehen: Bei diesem Beispiel wird davon ausgegangen, dass ein Sperraufruf bei der Übertragung zur neuen Aktivität ausgelöst wurde, und es enthält Suspend-/Resume-Ablaufverfolungen.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [End-to-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
