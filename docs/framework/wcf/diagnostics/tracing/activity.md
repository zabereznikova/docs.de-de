---
title: Aktivität
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: 3100d5bb60dc1b11d23b0705f4d6f23a3675ac51
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="activity"></a>Aktivität
Dieses Thema beschreibt die aktivitätsablaufverfolgungen in der Windows Communication Foundation (WCF)-aktivitätsablaufverfolgungs-Modell. Aktivitäten sind Verarbeitungseinheiten, mit deren Hilfe der Benutzer einen Fehlerbereich eingrenzen kann. Fehler, die in der gleichen Aktivität auftreten, hängen direkt zusammen. Ein Vorgang schlägt z.&#160;B. fehl, weil eine Nachrichtenentschlüsselung fehlgeschlagen ist. Die Ablaufverfolgungen für den Vorgangs- und den Nachrichtenverschlüsselungsfehler treten in der gleichen Aktivität auf und zeigen eine direkte Verbindung zwischen dem Verschlüsselungsfehler und dem Anforderungsfehler.  
  
## <a name="configuring-activity-tracing"></a>Konfigurieren der Aktivitätsablaufverfolgung  
 WCF bietet vordefinierte Aktivitäten für die Verarbeitung von Anwendungen (siehe [Aktivitätsliste](../../../../../docs/framework/wcf/diagnostics/tracing/activity-list.md)). Sie können Aktivitäten auch programmgesteuert definieren, um Benutzerablaufverfolgungen zu gruppieren. Weitere Informationen finden Sie unter [Ausgeben von Benutzercode-Ablaufverfolgungen](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
 Verwenden, um aktivitätsablaufverfolgungen zur Laufzeit auszugeben, die `ActivityTracing` Einstellung für die `System.ServiceModel` trace Quelle oder andere WCF oder benutzerdefinierte Ablaufverfolgungsquellen wie der folgende Konfigurationscode veranschaulicht.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Weitere Informationen zu dem Konfigurationselement und Attribute, die verwendet wird, erfahren Sie unter der [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) Thema.  
  
## <a name="viewing-activities"></a>Anzeigen von Aktivitäten  
 Sie können die Aktivitäten und ihre Nützlichkeit in Anzeigen der [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Wenn ActivityTracing aktiviert wird, sortiert dieses Tool die Ablaufverfolgungen basierend auf der Aktivität. Sie können auch Ablaufverfolgungsübertragungen anzeigen. Eine Ablaufverfolgungsübertragung gibt an, wie verschiedene Aktivitäten zusammenhängen. Sie sehen, dass eine bestimmte Aktivität das Starten einer anderen Aktivität verursachte. Eine Nachrichtenanforderung hat z.&#160;B. einen Sicherheitshandshake gestartet, um ein Token für eine sichere Konversation abzurufen.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Korrelation von Aktivitäten in Service Trace Viewer  
 Das Service Trace Viewer-Tool stellt zwei Aktivitätsansichten bereit:  
  
-   **Liste** Ansicht, in dem die Aktivitäts-ID zum Korrelieren von ablaufverfolgungen prozessübergreifend direkt verwendet wird. Ablaufverfolgungen aus unterschiedlichen Prozessen, z.&#160;B. Client und Dienst, jedoch mit der gleichen Aktivitäts-ID werden in der gleichen Aktivität gruppiert. Wenn folglich ein Fehler im Dienst auftritt, der wiederum einen Fehler auf dem Client verursacht, werden beide Fehler in der gleichen Aktivitätsansicht im Tool angezeigt.  
  
-   **Diagramm** Ansicht, in denen Aktivitäten nach Prozessen gruppiert werden. In dieser Ansicht verwalten ein Client und ein Dienst mit der gleichen Aktivitäts-ID ihre Ablaufverfolgungen in unterschiedlichen Aktivitäten. Zur Korrelation von Aktivitäten mit der gleichen Aktivitäts-ID, jedoch in unterschiedlichen Prozessen, zeigt das Tool den Fluss der Nachrichten zwischen den verwandten Aktivitäten.  
  
 Weitere Informationen und eine grafische Ansicht des Service Trace Viewer-Tools finden Sie unter finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) und [mithilfe von Service Trace Viewer für korrelierte Ablaufverfolgungen anzeigen und Problembehandlung bei](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
## <a name="defining-the-scope-of-an-activity"></a>Definieren des Bereichs einer Aktivität  
 Eine Aktivität wird zur Entwurfszeit definiert und bezeichnet eine logische Arbeitseinheit. Ausgegebene Ablaufverfolgungen mit dem gleichen Aktivitätsbezeichner hängen direkt zusammen, sie gehören zur gleichen Aktivität. Da eine Aktivität über Endpunktgrenzen hinausgehen kann (eine Anforderung), werden zwei Bereiche für eine Aktivität definiert.  
  
-   Bereich (`Global`), pro Anwendung. In diesem Bereich wird die Aktivität nach ihrem global eindeutigen 128-Bit-Aktivitätsbezeichner, der gAId, identifiziert. Die gAId wird über Endpunkte hinaus weitergegeben.  
  
-   Bereich (`Local`), pro Endpunkt. In diesem Bereich wird die Aktivität nach ihrer gAId identifiziert sowie nach dem Namen der Ablaufverfolgungsquelle, die die Aktivitätsablaufverfolgungen ausgibt, und nach der Prozess-ID. Diese Dreiergruppe bildet die lokale Aktivitäts-ID, die lAId. Mit der lAId werden die (lokalen) Grenzen einer Aktivität definiert.  
  
## <a name="trace-schema"></a>Ablaufverfolgungsschema  
 Ablaufverfolgungen können mit einem beliebigen Schema und über verschiedene Microsoft-Plattformen hinweg ausgegeben werden. "e2e" (für "End-End") ist ein häufig verwendetes Schema. Dieses Schema umfasst einen 128-Bit-Bezeichner (gAId), den Namen der Ablaufverfolgungsquelle und die Prozess-ID. In verwaltetem Code gibt <xref:System.Diagnostics.XmlWriterTraceListener> Ablaufverfolgungen im E2E-Schema aus.  
  
 Entwickler können die mit einer Ablaufverfolgung ausgegebene AID festlegen, indem sie die <xref:System.Diagnostics.CorrelationManager.ActivityId%2A>-Eigenschaft mit einer GUID zum lokalen Threadspeicher (Thread Local Storage, TLS) festlegen. Dies wird im folgenden Beispiel veranschaulicht:  
  
```  
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```  
  
 Das Festlegen der gAId im TLS wird deutlich, wenn Ablaufverfolgungen unter Verwendung einer Ablaufverfolgungsquelle ausgegeben werden, wie im folgenden Beispiel veranschaulicht wird.  
  
```  
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 Die ausgegebene Ablaufverfolgung enthält die gAId, die sich aktuell im TLS befindet, den als Parameter an den Konstruktor der Ablaufverfolgungsquelle übergebenen Namen der Ablaufverfolgungsquelle und die ID des aktuellen Prozesses.  
  
## <a name="activity-lifetime"></a>Lebensdauer einer Aktivität  
 Streng genommen beginnt das Auftreten einer Aktivität mit der ersten Verwendung der Aktivitäts-ID in einer ausgegebenen Ablaufverfolgung und endet die Aktivität mit ihrer letzten Verwendung in einer ausgegebenen Ablaufverfolgung. <xref:System.Diagnostics> stellt eine vordefinierte Reihe von Ablaufverfolgungstypen bereit, einschließlich Start und Stop, mit denen die Lebensdauer einer Aktivität ausdrücklich angegeben werden kann.  
  
-   Start: Gibt den Beginn einer Aktivität an. Eine "Start"-Ablaufverfolgung stellt einen Datensatz zu Beginn eines neuen verarbeitungsmeilensteins bereit. Er enthält eine neue Aktivitäts-ID für eine bestimmte Ablaufverfolgungsquelle in einem bestimmten Prozess. Davon ausgenommen sind Weitergaben der Aktivitäts-ID über Endpunkte hinaus. In diesen Fällen wird ein "Start" pro Endpunkt angegeben. Das Erstellen eines neuen Threads zur Verarbeitung oder die Eingabe einer neuen öffentlichen Methode sind Beispiele für das Starten einer neuen Aktivität.  
  
-   Stop: Gibt das Ende einer Aktivität an. Eine "Stop"-Ablaufverfolgung stellt einen Datensatz am Ende eines vorhandenen verarbeitungsmeilensteins bereit. Sie enthält eine vorhandene Aktivitäts-ID für eine bestimmte Ablaufverfolgungsquelle in einem bestimmten Prozess, sofern die Aktivitäts-ID nicht über Endpunkte hinaus weitergegeben wird. In diesem Fall wird ein "Stop" pro Endpunkt angegeben.  Beenden einer Aktivität zählen Beenden eines Verarbeitungsthreads oder Beenden einer Methode, deren Beginn mit einer "Start"-Ablaufverfolgung angegeben wurde.  
  
-   Suspend: Gibt eine Unterbrechung der Verarbeitung einer Aktivität an. Eine "Suspend"-Ablaufverfolgung enthält eine vorhandene Aktivitäts-ID, deren Verarbeitung voraussichtlich zu einem späteren Zeitpunkt fortzusetzen. Mit dieser ID werden keine Ablaufverfolgungen zwischen den Ereignissen Suspend und Resume von der aktuellen Ablaufverfolgungsquelle ausgegeben. Zu den Beispielen hierfür gehören das Anhalten einer Aktivität bei einem Aufruf einer externen Bibliotheksfunktion oder das Warten auf eine Ressource, beispielsweise einen E/A-Abschlussanschluss.  
  
-   Resume: Gibt die Wiederaufnahme der Verarbeitung einer Aktivität an. Eine "Resume"-Ablaufverfolgung enthält eine vorhandene Aktivitäts-Id, deren letzte ausgegebene Ablaufverfolgung aus der aktuellen Ablaufverfolgungsquelle eine "Suspend"-Ablaufverfolgung war. Zu den Beispielen hierfür gehören die Rückgabe eines Aufrufs einer externen Bibliotheksfunktion oder das Signal einer Ressource, beispielsweise eines E/A-Abschlussanschlusses, zum Fortsetzen der Verarbeitung.  
  
-   Transfer: Da einige Aktivitäten durch andere verursacht werden, oder an andere Benutzer zu verknüpfen, können Aktivitäten über "Transfer"-ablaufverfolgungen mit anderen Aktivitäten verknüpft sein. Eine Übertragung (Transfer) zeichnet die speziellen Beziehungen zwischen Aktivitäten auf.  
  
 Start- und Stop-Ablaufverfolgungen sind für die Korrelation nicht entscheidend. Sie können jedoch dazu beitragen, die Leistung, die Profilerstellung und die Validierung des Aktivitätsbereichs zu verbessern.  
  
 Mithilfe dieser Typen können die Tools die Navigation in den Ablaufverfolgungsprotokollen optimieren und nach direkt zusammenhängenden Ereignissen derselben Aktivität suchen oder nach Ereignissen in verwandten Aktivitäten, wenn das Tool Transfer-Ablaufverfolgungen überwacht. Die Tools beenden z.&#160;B. die Analyse des Protokolls für eine bestimmte Aktivität, wenn eine Start/Stop-Ablaufverfolgung festgestellt wird.  
  
 Diese Ablaufverfolgungstypen können auch zur Profilerstellung verwendet werden. Ressourcen, die zwischen Start- und Stop-Kennzeichnungen verwendet werden, stellen die inklusive Zeit einer Aktivität dar, einschließlich enthaltener logischer Aktivitäten. Die Differenz der Zeitintervalle zwischen Suspend- und Resume-Ablaufverfolgungen ergibt die tatsächliche Aktivitätsdauer.  
  
 Auch die Stop-Ablaufverfolgung ist besonders hilfreich bei der Validierung des Bereichs der implementierten Aktivitäten. Wenn einige Verarbeitungsablaufverfolgungen nach der Stop-Ablaufverfolgung statt innerhalb einer bestimmten Aktivität auftreten, kann das auf einen Codefehler hinweisen.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Richtlinien zum Verwenden der Aktivitätsablaufverfolgung  
 Die folgenden Hinweise beziehen sich auf die Verwendung von ActivityTracing-Ablaufverfolgungen (Start, Stop, Suspend, Resume und Transfer).  
  
-   Die Ablaufverfolgung ist ein zyklisch gerichtetes Diagramm, keine Struktur. Sie können die Steuerung an eine Aktivität zurückgeben, die eine Aktivität erzeugt hat.  
  
-   Eine Aktivität kennzeichnet eine Verarbeitungsgrenze, die für den Administrator des Systems oder die Unterstützungsmöglichkeiten von Bedeutung sein kann.  
  
-   Jeder WCF-Methode, sowohl auf dem Client und Server, wird vom Beginn einer neuen Aktivität und anschließend (nach Abschluss der Arbeit) begrenzt, die die neue Aktivität zu beenden und die Rückgabe an die ambient-Aktivität.  
  
-   Lange andauernde (fortlaufende) Aktivitäten, wie z.&#160;B. das Überwachen von Verbindungen oder Warten auf Nachrichten, werden durch übereinstimmende Start/Stop-Kennzeichnungen dargestellt.  
  
-   Durch den Empfang oder die Verarbeitung einer Nachricht ausgelöste Aktivitäten werden durch Ablaufverfolgungsgrenzen dargestellt.  
  
-   Aktivitäten stellen Aktivitäten dar, nicht notwendigerweise Objekte. Eine Aktivität als interpretiert werden soll "das geschah bei. sein. sein. (sinnvolle Ausgabe einer Ablaufverfolgung stattfand)" interpretiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [End-to-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Ausgeben von Benutzercode-Ablaufverfolgungen](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)
