---
title: Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung
ms.date: 03/30/2017
ms.assetid: 05d2321c-8acb-49d7-a6cd-8ef2220c6775
ms.openlocfilehash: e1cd1443e96e7195127cb95e7ef1b2c4d6d9c176
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587754"
---
# <a name="using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting"></a>Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung

In diesem Thema wird das Format von Ablaufverfolgungsdaten und ihre Verwendung beschrieben. Dabei wird auch auf die Verwendung von Service Trace Viewer zur Problembehandlung in einer Anwendung eingegangen.

## <a name="using-the-service-trace-viewer-tool"></a>Verwenden des Service Trace Viewer-Tools

Mit dem Service Trace Viewer-Tool für Windows Communication Foundation (WCF) können Sie Diagnose Ablauf Verfolgungen, die von WCF-Listenern erzeugt werden, korrelieren, um die Fehlerursache zu ermitteln. Das Tool bietet Ihnen die Möglichkeit, Ablauf Verfolgungen leicht anzuzeigen, zu gruppieren und zu filtern, sodass Sie Probleme mit WCF-Diensten diagnostizieren, reparieren und überprüfen können. Weitere Informationen zur Verwendung dieses Tools finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md).

Dieses Thema enthält Screenshots von Ablauf Verfolgungen, die durch Ausführen des Beispiels für Ablauf [Verfolgung und Nachrichten Protokollierung](../../samples/tracing-and-message-logging.md) generiert werden, wenn Sie mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden. In diesem Thema werden der Ablaufverfolgungsinhalt, Aktivitäten und ihre Korrelation erläutert. Zudem wird beschrieben, wie eine große Zahl von Ablaufverfolgungen im Rahmen der Problembehandlung analysiert werden können.

## <a name="viewing-trace-content"></a>Anzeigen von Ablaufverfolgungsinhalt

Ein Ablaufverfolgungsereignis enthält die folgenden wichtigen Informationen:

- Aktivitätsname bei Festlegung

- Ausgabezeit

- Ablaufverfolgungsebene

- Name der Ablaufverfolgungsquelle.

- Prozessname

- Thread-ID

- Ein eindeutiger Bezeichner für die Ablauf Verfolgung, bei dem es sich um eine URL handelt, die auf ein Ziel in Microsoft-Dokumentation verweist, von dem Sie weitere Informationen zur Ablauf Verfolgung abrufen können.

 Alle diese können im oberen rechten Bereich des Service Trace Viewer angezeigt werden, oder Sie werden im Abschnitt " **grundlegende Informationen** " in der formatierten Ansicht des unteren rechten Bereichs angezeigt, wenn Sie eine Ablauf Verfolgung auswählen.

> [!NOTE]
> Wenn sich der Client und der Dienst auf demselben Computer befinden, können die Ablaufverfolgungen für beide Anwendungen eingesehen werden. Diese können mithilfe der Spalte **Prozess Name** gefiltert werden.

Zudem bietet die formatierte Ansicht eine Beschreibung der Ablaufverfolgung sowie zusätzliche detaillierte Informationen, sofern diese verfügbar sind. Dazu gehören Ausnahmeart und -nachricht, Aufruflisten, Nachrichtenaktion, Felder Von/Zu und andere Ausnahmeinformationen.

Die XML-Ansicht enthält die folgenden nützlichen XML-Tags:

- `<SubType>`(Ablauf Verfolgungs Ebene).

- `<TimeCreated>`.

- `<Source>`(Name der Ablauf Verfolgungs Quelle).

- `<Correlation>`(Aktivitäts-ID festgelegt, wenn die Ablauf Verfolgung ausgegeben wird).

- `<Execution>`(Prozess-und Thread-ID).

- `<Computer>`.

- `<ExtendedData>`einschließlich `<Action>` , `<MessageID>` und der `<ActivityId>` im Nachrichten Header festgelegte, wenn eine Nachricht gesendet wird.

Wenn Sie die Ablaufverfolgung "Sent a message over a channel" ("Nachricht über einen Kanal gesendet") prüfen, wird möglicherweise der folgende Inhalt angezeigt.

```xml
<E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
   <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
      <EventID>262163</EventID>
      <Type>3</Type>
      <SubType Name="Information">0</SubType>
      <Level>8</Level>
      <TimeCreated SystemTime="2006-08-04T18:45:30.8491051Z" />
      <Source Name="System.ServiceModel" />
       <Correlation ActivityID="{27c6331d-8998-43aa-a382-03239013a6bd}"/>
       <Execution ProcessName="client" ProcessID="1808" ThreadID="1" />
       <Channel />
       <Computer>TEST1</Computer>
   </System>
   <ApplicationData>
       <TraceData>
          <DataItem>
             <TraceRecord xmlns="http://schemas.microsoft.com/2004/10/E2ETraceEvent/TraceRecord" Severity="Information">
                 <TraceIdentifier>http://msdn.microsoft.com/library/System.ServiceModel.Channels.MessageSent.aspx</TraceIdentifier>
                 <Description>Sent a message over a channel.</Description>
                 <AppDomain>client.exe</AppDomain>
                 <Source>System.ServiceModel.Channels.ClientFramingDuplexSessionChannel/35191196</Source>
                <ExtendedData xmlns="http://schemas.microsoft.com/2006/08/ServiceModel/MessageTransmitTraceRecord">

                  <MessageProperties>
                     <AllowOutputBatching>False</AllowOutputBatching>
                  </MessageProperties>
                  <MessageHeaders>
                     <Action d4p1:mustUnderstand="1" xmlns:d4p1="http://www.w3.org/2003/05/soap-envelope" xmlns="http://www.w3.org/2005/08/addressing">http://Microsoft.ServiceModel.Samples/ICalculator/Multiply</Action>
                     <MessageID xmlns="http://www.w3.org/2005/08/addressing">urn:uuid:7c6670d8-4c9c-496e-b6a0-2ceb6db35338</MessageID>
                     <ActivityId CorrelationId="b02e2189-0816-4387-980c-dd8e306440f5" xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">27c6331d-8998-43aa-a382-03239013a6bd</ActivityId>
                     <ReplyTo xmlns="http://www.w3.org/2005/08/addressing">
                        <Address>http://www.w3.org/2005/08/addressing/anonymous</Address>
                    </ReplyTo>
                    <To d4p1:mustUnderstand="1" xmlns:d4p1="http://www.w3.org/2003/05/soap-envelope" xmlns="http://www.w3.org/2005/08/addressing">net.tcp://localhost/servicemodelsamples/service</To>
                  </MessageHeaders>
                  <RemoteAddress>net.tcp://localhost/servicemodelsamples/service</RemoteAddress>
                </ExtendedData>
            </TraceRecord>
          </DataItem>
       </TraceData>
   </ApplicationData>
</E2ETraceEvent>
```

## <a name="servicemodel-e2e-tracing"></a>ServiceModel E2E-Ablaufverfolgung

Wenn die Ablauf `System.ServiceModel` Verfolgungs Quelle mit einem anderen Wert als Off festgelegt wird `switchValue` , `ActivityTracing` erstellt WCF Aktivitäten und Übertragungen für die WCF-Verarbeitung.

Eine Aktivität ist eine logische Verarbeitungseinheit, die alle verknüpften Ablaufverfolgungen zusammenfasst. So können Sie beispielsweise eine Aktivität für jede Anforderung definieren. Übertragungen stellen eine kausale Beziehung zwischen Aktivitäten innerhalb von Endpunkten her. Durch die Weitergabe der Aktivitäts-ID können Sie Aktivitäten über Endpunkte hinweg verknüpfen. Dies kann durch Festlegen von `propagateActivity` = `true` in der Konfiguration an jedem Endpunkt erreicht werden. Aktivitäten, Übertragungen und Weitergabe ermöglichen es Ihnen, die Fehlerkorrelation durchzuführen. Auf diese Weise können Sie die Grundursache eines Fehlers schneller ermitteln.

Auf dem Client wird eine WCF-Aktivität für jeden Objektmodell Rückruf erstellt (z. b. Open ChannelFactory, Add, Divide usw.). Jeder der Vorgangs Aufrufe wird in einer Aktivität zum Verarbeiten von Aktionen verarbeitet.

Im folgenden Screenshot, der aus dem [Ablaufverfolgungs-und Nachrichten Protokollierungs](../../samples/tracing-and-message-logging.md) Beispiel extrahiert wurde, wird im linken Bereich die Liste der Aktivitäten angezeigt, die im Client Prozess nach Erstellungszeit sortiert wurden. Es folgt eine chronologische Liste von Aktivitäten:

- Kanalfactory erstellt (ClientBase).

- Kanalfactory geöffnet.

- Add-Aktion (Hinzufügen) verarbeitet.

- Set Up Secure Session (Sichere Sitzung einrichten) ausgeführt (nach erster Anforderung ERFOLGT) und drei Sicherheitsinfrastruktur-Antwortnachrichten verarbeitet: RST, RSTR, SCT (Process message 1, 2, 3; Nachricht 1, 2, 3 verarbeiten).

- Anforderungen Subtract, Multiply und Divide (Subtrahieren, Multiplizieren und Dividieren) verarbeitet.

- Kanalfactory geschlossen, dabei sichere Sitzung beendet und Sicherheitsantwort Cancel (Abbrechen) verarbeitet.

 Die Sicherheitsinfrastrukturnachrichten sind aufgrund der Bindung wsHttpBinding sichtbar.

> [!NOTE]
> In WCF zeigen wir Antwort Nachrichten, die anfänglich in einer separaten Aktivität verarbeitet werden (Prozess Nachricht), bevor wir Sie mit der entsprechenden Prozess Aktions Aktivität korrelieren, die die Anforderungs Nachricht über eine Übertragung einschließt. Das geschieht sowohl für Infrastrukturnachrichten als auch für asynchrone Anforderungen, da die Nachricht geprüft, der activityId-Header gelesen und die vorhandene ProcessAction-Aktivität mit der ID ermittelt werden muss, um die Korrelation vorzunehmen. Bei synchronen Anforderungen wird die Antwort blockiert, weshalb bekannt ist, mit welcher Verarbeitungsaktion die Antwort verknüpft ist.

In der folgenden Abbildung werden die WCF-Client Aktivitäten angezeigt, die nach Erstellungszeit (linker Bereich) und ihren zugehörigen Aktivitäten und Ablauf Verfolgungen (oberer rechten Bereich) aufgelistet sind:

![Screenshot der nach Erstellungszeit aufgelisteten WCF-Client Aktivitäten.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-activities-creation-time.gif)

Wenn Sie im linken Bereich eine Aktivität auswählen, werden die verschachtelten Aktivitäten und Ablaufverfolgungen im rechten oberen Bereich angezeigt. Dabei handelt es sich somit um eine auf der Basis der ausgewählten übergeordneten Aktivität verkürzte hierarchische Ansicht der Aktivitätenliste auf der linken Seite. Da die ausgewählte Verarbeitungsaktion Add die erste Anforderung ist, enthält diese Aktivität die Aktivität Set Up Secure Session (Übertragung nach, Rückübertragung von) sowie Ablaufverfolgungen für die eigentliche Verarbeitung der Add-Aktion.

Wenn Sie im linken Bereich auf die Aktivität "Prozess Aktion hinzufügen" doppelklicken, wird eine grafische Darstellung der WCF-Client Aktivitäten angezeigt, die sich auf Hinzufügen beziehen. Die erste Aktivität auf der linken Seite ist die Stammaktivität (0000), bei der es sich um die Standardaktivität handelt. WCF überträgt aus der Ambient-Aktivität heraus. Wenn dies nicht definiert ist, überträgt WCF aus 0000. Im vorliegenden Fall überträgt die zweite Aktivität, die Verarbeitungsaktion Add, aus 0 heraus. Dann wird Set Up Secure Session (Sichere Sitzung einrichten) angezeigt.

Die folgende Abbildung zeigt eine Diagramm Ansicht der WCF-Client Aktivitäten, insbesondere Ambient-Aktivität (hier 0), Prozess Aktion und Einrichten einer sicheren Sitzung:

![Diagramm im Ablauf Verfolgungs Viewer, der Ambient-Aktivität und Prozess Aktion anzeigt.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-activities-graph-ambient-process.gif)

Im oberen rechten Bereich sind alle Ablaufverfolgungen zu sehen, die mit der Process Action Add-Aktivität verknüpft sind. Das bedeutet, in ein und derselben Aktivität wurde die Anforderungsnachricht gesendet ("Sent a message over a channel", "Nachricht über einen Kanal gesendet") und die Antwort empfangen ("Received a message over a channel", "Nachricht über einen Kanal empfangen"). Dies wird im folgenden Diagramm dargestellt. Zur besseren Übersichtlichkeit ist die Set Up Secure Session-Aktivität im Diagramm reduziert.

Die folgende Abbildung zeigt eine Liste der Ablauf Verfolgungen für die Aktivität "Prozess Aktion". Wir senden die Anforderung und empfangen die Antwort in derselben Aktivität.

![Screenshot des Trace Viewer mit einer Liste von Ablauf Verfolgungen für die Aktivität "Prozess Aktion"](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/process-action-traces.gif)

Hier werden Client Ablauf Verfolgungen nur aus Gründen der Übersichtlichkeit geladen, aber Dienst Ablauf Verfolgungen (empfangene Anforderungs Nachrichten und gesendete Antwort Nachrichten) werden in derselben Aktivität angezeigt, wenn Sie auch im Tool geladen werden und `propagateActivity` `true.` in einer späteren Abbildung festgelegt wurde.

Im-Dienst wird das-Aktivitäts Modell den WCF-Konzepten wie folgt zugeordnet:

1. Ein ServiceHost wird erstellt und geöffnet (dadurch werden möglicherweise mehrere hostbezogene Aktivitäten erzeugt, z.&#160;B. im Falle der Sicherheit).

2. Es wird eine Lauschaktivität für jeden Listener im ServiceHost erstellt (mit Übertragung in und aus Open ServiceHost).

3. Wenn der Listener eine vom Client initiierte Kommunikations Anforderung erkennt, wird er auf die Aktivität "Empfangs Bytes" übertragen, in der alle vom Client gesendeten Bytes verarbeitet werden. In dieser Aktivität sind alle Verbindungsfehler erkennbar, die während der Client-Dienst-Interaktion aufgetreten sind.

4. Für jeden empfangenen Satz von Bytes, der einer Nachricht entspricht, werden diese Bytes in einer "Process Message"-Aktivität verarbeitet, in der das WCF-Nachrichten Objekt erstellt wird. In dieser Aktivität sind Fehler aufgrund eines ungültigen Umschlags oder einer falsch formatierten Nachricht erkennbar.

5. Sobald die Nachricht erstellt wird, erfolgt die Übertragung zu einer Process Action-Aktivität. Wenn `propagateActivity` sowohl für den Client als auch für den Dienst auf `true` festgelegt ist, verfügt diese Aktivität über dieselbe ID wie die auf dem Client definierte und zuvor beschriebene. Aus dieser Phase profitieren wir von der direkten Korrelation über Endpunkte hinweg, da alle in WCF ausgegebenen Ablauf Verfolgungen, die mit der Anforderung verknüpft sind, sich in derselben Aktivität befinden, einschließlich der Verarbeitung der Antwortnachricht.

6. Für die Out-of-Process-Aktion erstellen wir eine Aktivität "Benutzercode ausführen", um Ablauf Verfolgungen zu isolieren, die in Benutzercode von den in WCF ausgegebenen ausgegeben werden. Im vorherigen Beispiel wird die Ablauf Verfolgung "der Dienst sendet eine Antwort hinzufügen" in der Aktivität "Benutzercode ausführen" ausgegeben, die sich nicht in der vom Client weiter gegebenen Aktivität befindet (falls zutreffend).

In der nachfolgenden Abbildung ist die erste Aktivität auf der linken Seite die Stammaktivität (0000), bei der es sich um die Standardaktivität handelt. Die nächsten drei Aktivitäten dienen dazu, den ServiceHost zu öffnen. Die Aktivität in Spalte&#160;5 ist der Listener, und die übrigen Aktivitäten (6 bis 8) beschreiben die WCF-Verarbeitung einer Nachricht, von der Byteverarbeitung bis zur Benutzercodeaktivierung.

Die folgende Abbildung zeigt eine Diagramm Ansicht der WCF-Dienst Aktivitäten:

![Screenshot des Trace Viewer, der eine Liste der WCF-Dienst Aktivitäten anzeigt](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-service-activities.gif)

Der folgende Screenshot zeigt die Aktivitäten sowohl des Clients als auch des Diensts. Die Process Action Add-Aktivität ist orange hervorgehoben. Pfeile verknüpfen die Anforderungs- und die Antwortnachrichten, die vom Client und vom Dienst gesendet und empfangen werden. Die ProcessAction-Ablaufverfolgungen sind über Prozesse im Diagramm verteilt, werden im oberen rechten Bereich jedoch als Teil derselben Aktivität angezeigt. In diesem Bereich sind Clientablaufverfolgungen für gesendete Nachrichten gefolgt von Dienstablaufverfolgungen für empfangene und verarbeitete Nachrichten zu sehen.

Die folgenden Bilder zeigen eine Diagramm Ansicht der WCF-Client-und Dienst Aktivitäten.

![Graph aus dem Trace Viewer, der WCF-Client-und Dienst Aktivitäten anzeigt.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-service-activities.gif)

Im folgenden Fehlerszenario werden Fehler- und Warnungsablaufverfolgungen im Dienst und auf dem Client verknüpft. Zunächst wird eine Ausnahme in Benutzercode für den Dienst ausgelöst (grüne Aktivität ganz rechts mit einer Warnungsablaufverfolgung für die Ausnahme "The service cannot process this request in user code", "Der Dienst kann diese Anforderung nicht in Benutzercode verarbeiten"). Beim Senden der Antwort an den Client wird erneut eine Warnungsablaufverfolgung ausgegeben, um die Fehlernachricht anzugeben (rosafarbene Aktivität links). Der Client schließt sodann seinen WCF-Client (gelbe Aktivität unten links), der die Verbindung zum Dienst abbricht. Der Dienst löst einen Fehler aus (längste rosafarbene Aktivität rechts).

![Verwenden des Ablaufverfolgungs-Viewers](media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")

Dienst- und clientübergreifende Fehlerkorrelation

Das Beispiel, das verwendet wird, um diese Ablaufverfolgungen zu generieren, ist eine Reihe von synchronen Anforderungen mit der Bindung wsHttpBinding. Abweichungen von diesem Diagramm treten bei Szenarien ohne Sicherheit oder bei asynchronen Anforderungen auf, bei denen die ProcessAction-Aktivität die Anfangs- und Endvorgänge umfasst, die den asynchronen Aufruf bilden, und Übertragungen zu einer Rückrufaktivität zeigt. Weitere Informationen zu weiteren Szenarien finden Sie unter [End-to-End-Ablauf Verfolgungs Szenarien](end-to-end-tracing-scenarios.md).

## <a name="troubleshooting-using-the-service-trace-viewer"></a>Problembehandlung mit Service Trace Viewer

Wenn Sie Ablaufverfolgungsdateien in das Service Trace Viewer-Tool laden, können Sie jede beliebige rote oder gelbe Aktivität im linken Bereich auswählen, um die Ursache für ein Problem in Ihrer Anwendung zu ermitteln. Die Aktivität 000 verfügt i.&#160;d.&#160;R. über nicht behandelte Ausnahmen, mit denen sich der Benutzer befassen muss.

In der folgenden Abbildung wird gezeigt, wie Sie eine rote oder gelbe Aktivität auswählen, um die Ursache eines Problems zu finden.
![Screenshot der roten oder gelben Aktivitäten, um die Ursache eines Problems zu ermitteln.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/service-trace-viewer.gif)

Im oberen rechten Bereich können Sie Ablaufverfolgungen für die Aktivität prüfen, die Sie auf der linken Seite ausgewählt haben. Sie können dann rote oder gelbe Ablaufverfolgungen in diesem Bereich prüfen und sehen, wie sie korrelieren. Im vorangehenden Diagramm sind Warnungsablaufverfolgungen sowohl für den Client als auch für den Dienst in derselben Process Action-Aktivität erkennbar.

Wenn diese Ablaufverfolgungen nicht auf die Grundursache des Fehlers schließen lassen, können Sie auf die ausgewählte Aktivität im linken Bereich doppelklicken (hier Process Action). Das Diagramm mit den zugehörigen Aktivitäten wird dann angezeigt. Anschließend können Sie verwandte Aktivitäten erweitern (indem Sie auf die "+"-Zeichen klicken), um die erste ausgegebene Ablauf Verfolgung in rot oder gelb in einer verwandten Aktivität zu suchen. Erweitern Sie nach und nach die Aktivitäten, die direkt vor der betreffenden roten oder gelben Ablaufverfolgung ausgeführt wurden, und verfolgen Sie die Übertragungen zu verknüpften Aktivitäten oder Nachrichtenflüsse über Endpunkte hinweg, bis Sie die Grundursache des Problems gefunden haben.

![Verwenden des Ablaufverfolgungs-Viewers](media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")

Erweitern von Aktivitäten zur Ermittlung der Ursache eines Problems

Wenn die ServiceModel `ActivityTracing` deaktiviert, aber die ServiceModel-Ablaufverfolgung aktiviert ist, werden ServiceModel-Ablaufverfolgungen in der Aktivität 0000 ausgegeben. In diesem Fall ist es jedoch aufwändiger, die Korrelation dieser Ablaufverfolgungen zu verstehen.

Wenn die Nachrichtenprotokollierung aktiviert ist, können Sie auf der Registerkarte Nachricht nachsehen, welche Nachricht vom Fehler betroffen ist. Wenn Sie auf eine rote oder gelbe Nachricht doppelklicken, wird die Diagrammansicht der zugehörigen Aktivitäten angezeigt. Das sind die Aktivitäten, die am engsten mit der Anforderung verknüpft sind, bei der ein Fehler aufgetreten ist.

![Screenshot des Trace Viewer mit aktivierter Nachrichten Protokollierung.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/message-logging-enabled.gif)

Um mit der Problembehandlung zu beginnen, können Sie auch eine rote oder gelbe Nachrichten Ablauf Verfolgung auswählen und darauf doppelklicken, um die Ursache zu verfolgen.

## <a name="see-also"></a>Weitere Informationen

- [End-to-End-Ablaufverfolgungsszenarien](end-to-end-tracing-scenarios.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Ablaufverfolgung](index.md)
