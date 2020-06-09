---
title: Aktivität
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: 41de6b9458feb4e1898eeac6635b74c4617885d6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602140"
---
# <a name="activity"></a>Aktivität
In diesem Thema werden Aktivitäts Ablauf Verfolgungen im Windows Communication Foundation (WCF)-Ablauf Verfolgungs Modell beschrieben. Aktivitäten sind Verarbeitungseinheiten, mit deren Hilfe der Benutzer einen Fehlerbereich eingrenzen kann. Fehler, die in der gleichen Aktivität auftreten, hängen direkt zusammen. Ein Vorgang schlägt z.&#160;B. fehl, weil eine Nachrichtenentschlüsselung fehlgeschlagen ist. Die Ablaufverfolgungen für den Vorgangs- und den Nachrichtenverschlüsselungsfehler treten in der gleichen Aktivität auf und zeigen eine direkte Verbindung zwischen dem Verschlüsselungsfehler und dem Anforderungsfehler.  
  
## <a name="configuring-activity-tracing"></a>Konfigurieren der Aktivitätsablaufverfolgung  
 WCF stellt vordefinierte Aktivitäten für die Verarbeitung von Anwendungen bereit (siehe [Aktivitäts Liste](activity-list.md)). Sie können Aktivitäten auch programmgesteuert definieren, um Benutzerablaufverfolgungen zu gruppieren. Weitere Informationen finden Sie unter ausgeben von [Benutzer Code-](emitting-user-code-traces.md)Ablauf Verfolgungen.  
  
 Um Aktivitäts Ablauf Verfolgungen zur Laufzeit auszugeben, verwenden Sie die- `ActivityTracing` Einstellung für die Ablauf `System.ServiceModel` Verfolgungs Quelle oder andere WCF-oder benutzerdefinierte Ablauf Verfolgungs Quellen, wie im folgenden Konfigurations Code veranschaulicht.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Weitere Informationen zum verwendeten Konfigurationselement und den verwendeten Attributen finden Sie im Thema [Konfigurieren](configuring-tracing.md) der Ablauf Verfolgung.  
  
## <a name="viewing-activities"></a>Anzeigen von Aktivitäten  
 Sie können die Aktivitäten und deren Dienstprogramm im [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)anzeigen. Wenn ActivityTracing aktiviert wird, sortiert dieses Tool die Ablaufverfolgungen basierend auf der Aktivität. Sie können auch Ablaufverfolgungsübertragungen anzeigen. Eine Ablaufverfolgungsübertragung gibt an, wie verschiedene Aktivitäten zusammenhängen. Sie sehen, dass eine bestimmte Aktivität das Starten einer anderen Aktivität verursachte. Eine Nachrichtenanforderung hat z.&#160;B. einen Sicherheitshandshake gestartet, um ein Token für eine sichere Konversation abzurufen.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Korrelation von Aktivitäten in Service Trace Viewer  
 Das Service Trace Viewer-Tool stellt zwei Aktivitätsansichten bereit:  
  
- **Listen** Ansicht, in der die Aktivitäts-ID verwendet wird, um Ablauf Verfolgungen Prozess übergreifend direkt zu korrelieren. Ablaufverfolgungen aus unterschiedlichen Prozessen, z.&#160;B. Client und Dienst, jedoch mit der gleichen Aktivitäts-ID werden in der gleichen Aktivität gruppiert. Wenn folglich ein Fehler im Dienst auftritt, der wiederum einen Fehler auf dem Client verursacht, werden beide Fehler in der gleichen Aktivitätsansicht im Tool angezeigt.  
  
- **Diagramm** Ansicht, in der Aktivitäten nach Prozessen gruppiert werden. In dieser Ansicht verwalten ein Client und ein Dienst mit der gleichen Aktivitäts-ID ihre Ablaufverfolgungen in unterschiedlichen Aktivitäten. Zur Korrelation von Aktivitäten mit der gleichen Aktivitäts-ID, jedoch in unterschiedlichen Prozessen, zeigt das Tool den Fluss der Nachrichten zwischen den verwandten Aktivitäten.  
  
 Weitere Informationen und eine grafische Ansicht des Service Trace Viewer-Tools finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md) und [Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.  
  
## <a name="defining-the-scope-of-an-activity"></a>Definieren des Bereichs einer Aktivität  
 Eine Aktivität wird zur Entwurfszeit definiert und bezeichnet eine logische Arbeitseinheit. Ausgegebene Ablaufverfolgungen mit dem gleichen Aktivitätsbezeichner hängen direkt zusammen, sie gehören zur gleichen Aktivität. Da eine Aktivität über Endpunktgrenzen hinausgehen kann (eine Anforderung), werden zwei Bereiche für eine Aktivität definiert.  
  
- Bereich (`Global`), pro Anwendung. In diesem Bereich wird die Aktivität nach ihrem global eindeutigen 128-Bit-Aktivitätsbezeichner, der gAId, identifiziert. Die gAId wird über Endpunkte hinaus weitergegeben.  
  
- Bereich (`Local`), pro Endpunkt. In diesem Bereich wird die Aktivität durch die zugehörige gAId identifiziert, zusammen mit dem Namen der Ablauf Verfolgungs Quelle, die die Aktivitäts Ablauf Verfolgungen und die Prozess-ID ausgibt. Dieses Triplett bildet die lokale Aktivitäts-ID, die festgelegt wurde. Mit der lAId werden die (lokalen) Grenzen einer Aktivität definiert.  
  
## <a name="trace-schema"></a>Ablaufverfolgungsschema  
 Ablaufverfolgungen können mit einem beliebigen Schema und über verschiedene Microsoft-Plattformen hinweg ausgegeben werden. "e2e" (für "End-to-End") ist ein häufig verwendetes Schema. Dieses Schema umfasst einen 128-Bit-Bezeichner (gAId), den Namen der Ablaufverfolgungsquelle und die Prozess-ID. In verwaltetem Code gibt <xref:System.Diagnostics.XmlWriterTraceListener> Ablaufverfolgungen im E2E-Schema aus.  
  
 Entwickler können die mit einer Ablaufverfolgung ausgegebene AID festlegen, indem sie die <xref:System.Diagnostics.CorrelationManager.ActivityId%2A>-Eigenschaft mit einer GUID zum threadlokalen Speicher (Thread Local Storage, TLS) festlegen. Das wird im folgenden Beispiel veranschaulicht.  
  
```csharp
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```
  
 Das Festlegen der gAId im TLS wird deutlich, wenn Ablaufverfolgungen unter Verwendung einer Ablaufverfolgungsquelle ausgegeben werden, wie im folgenden Beispiel veranschaulicht wird.  
  
```csharp
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 Die ausgegebene Ablaufverfolgung enthält die gAId, die sich aktuell im TLS befindet, den als Parameter an den Konstruktor der Ablaufverfolgungsquelle übergebenen Namen der Ablaufverfolgungsquelle und die ID des aktuellen Prozesses.  
  
## <a name="activity-lifetime"></a>Lebensdauer einer Aktivität  
 Streng genommen beginnt das Auftreten einer Aktivität mit der ersten Verwendung der Aktivitäts-ID in einer ausgegebenen Ablaufverfolgung und endet die Aktivität mit ihrer letzten Verwendung in einer ausgegebenen Ablaufverfolgung. <xref:System.Diagnostics> stellt eine vordefinierte Reihe von Ablaufverfolgungstypen bereit, einschließlich Start und Stop, mit denen die Lebensdauer einer Aktivität ausdrücklich angegeben werden kann.  
  
- Start: Gibt den Beginn einer Aktivität an. Eine "Start"-Ablauf Verfolgung stellt einen Datensatz für den Beginn eines neuen Verarbeitungs Meilensteins bereit. Er enthält eine neue Aktivitäts-ID für eine bestimmte Ablaufverfolgungsquelle in einem bestimmten Prozess. Davon ausgenommen sind Weitergaben der Aktivitäts-ID über Endpunkte hinaus. In diesen Fällen wird ein "Start" pro Endpunkt angegeben. Das Erstellen eines neuen Threads zur Verarbeitung oder die Eingabe einer neuen öffentlichen Methode sind Beispiele für das Starten einer neuen Aktivität.  
  
- Stop: Gibt das Ende einer Aktivität an. Eine "beenden"-Ablauf Verfolgung stellt einen Datensatz zum Beenden eines vorhandenen Verarbeitungs Meilensteins bereit. Sie enthält eine vorhandene Aktivitäts-ID für eine bestimmte Ablaufverfolgungsquelle in einem bestimmten Prozess, sofern die Aktivitäts-ID nicht über Endpunkte hinaus weitergegeben wird. In diesem Fall wird ein "Stop" pro Endpunkt angegeben.  Beispiele für das Beenden einer Aktivität sind das Beenden eines Verarbeitungs Threads oder das Beenden einer Methode, deren Anfang mit einer "Start"-Ablauf Verfolgung gekennzeichnet wurde.  
  
- Suspend: Gibt eine Unterbrechung der Verarbeitung einer Aktivität an. Eine "Suspend"-Ablauf Verfolgung enthält eine vorhandene Aktivitäts-ID, deren Verarbeitung voraussichtlich zu einem späteren Zeitpunkt fortgesetzt wird. Mit dieser ID werden keine Ablaufverfolgungen zwischen den Ereignissen Suspend und Resume von der aktuellen Ablaufverfolgungsquelle ausgegeben. Zu den Beispielen hierfür gehören das Anhalten einer Aktivität bei einem Aufruf einer externen Bibliotheksfunktion oder das Warten auf eine Ressource, beispielsweise einen E/A-Abschlussanschluss.  
  
- Resume: Gibt die Wiederaufnahme der Verarbeitung einer Aktivität an. Eine "Resume"-Ablauf Verfolgung enthält eine vorhandene Aktivitäts-ID, deren letzte ausgegebene Ablauf Verfolgung aus der aktuellen Ablauf Verfolgungs Quelle eine "Suspend"-Ablauf Verfolgung war. Zu den Beispielen hierfür gehören die Rückgabe eines Aufrufs einer externen Bibliotheksfunktion oder das Signal einer Ressource, beispielsweise eines E/A-Abschlussanschlusses, zum Fortsetzen der Verarbeitung.  
  
- Übertragung: da einige Aktivitäten durch andere verursacht werden oder sich auf andere Aktivitäten beziehen, können Aktivitäten über Übertragungs Ablauf Verfolgungen mit anderen Aktivitäten verknüpft werden. Eine Übertragung (Transfer) zeichnet die speziellen Beziehungen zwischen Aktivitäten auf.  
  
 Start- und Stop-Ablaufverfolgungen sind für die Korrelation nicht entscheidend. Sie können jedoch dazu beitragen, die Leistung, die Profilerstellung und die Validierung des Aktivitätsbereichs zu verbessern.  
  
 Mithilfe dieser Typen können die Tools die Navigation in den Ablaufverfolgungsprotokollen optimieren und nach direkt zusammenhängenden Ereignissen derselben Aktivität suchen oder nach Ereignissen in verwandten Aktivitäten, wenn das Tool Transfer-Ablaufverfolgungen überwacht. Die Tools beenden z.&#160;B. die Analyse des Protokolls für eine bestimmte Aktivität, wenn eine Start/Stop-Ablaufverfolgung festgestellt wird.  
  
 Diese Ablaufverfolgungstypen können auch zur Profilerstellung verwendet werden. Ressourcen, die zwischen Start- und Stop-Kennzeichnungen verwendet werden, stellen die inklusive Zeit einer Aktivität dar, einschließlich enthaltener logischer Aktivitäten. Die Differenz der Zeitintervalle zwischen Suspend- und Resume-Ablaufverfolgungen ergibt die tatsächliche Aktivitätsdauer.  
  
 Auch die Stop-Ablaufverfolgung ist besonders hilfreich bei der Validierung des Bereichs der implementierten Aktivitäten. Wenn einige Verarbeitungsablaufverfolgungen nach der Stop-Ablaufverfolgung statt innerhalb einer bestimmten Aktivität auftreten, kann das auf einen Codefehler hinweisen.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Richtlinien zum Verwenden der Aktivitätsablaufverfolgung  
 Die folgenden Hinweise beziehen sich auf die Verwendung von ActivityTracing-Ablaufverfolgungen (Start, Stop, Suspend, Resume und Transfer).  
  
- Die Ablaufverfolgung ist ein zyklisch gerichtetes Diagramm, keine Struktur. Sie können die Steuerung an eine Aktivität zurückgeben, die eine Aktivität erzeugt hat.  
  
- Eine Aktivität kennzeichnet eine Verarbeitungsgrenze, die für den Administrator des Systems oder die Unterstützungsmöglichkeiten von Bedeutung sein kann.  
  
- Jede WCF-Methode, die sowohl auf dem Client als auch auf dem Server ausgeführt wird, wird durch das Starten einer neuen Aktivität, anschließend (nach Abschluss der Arbeit) durch das Beenden der neuen Aktivität und das zurückkehren zur Ambient-Aktivität gebunden.  
  
- Lange andauernde (fortlaufende) Aktivitäten, wie z.&#160;B. das Überwachen von Verbindungen oder Warten auf Nachrichten, werden durch übereinstimmende Start/Stop-Kennzeichnungen dargestellt.  
  
- Durch den Empfang oder die Verarbeitung einer Nachricht ausgelöste Aktivitäten werden durch Ablaufverfolgungsgrenzen dargestellt.  
  
- Aktivitäten stellen Aktivitäten dar, nicht notwendigerweise Objekte. Eine Aktivität sollte wie folgt interpretiert werden: "Dies war passiert, als. . . (sinnvolle Ausgabe einer Ablaufverfolgung stattfand)" interpretiert werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren der Ablaufverfolgung](configuring-tracing.md)
- [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [End-to-End-Ablaufverfolgungsszenarien](end-to-end-tracing-scenarios.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Ausgeben von Benutzercode-Ablaufverfolgungen](emitting-user-code-traces.md)
