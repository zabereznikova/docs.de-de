---
title: Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung
ms.date: 03/30/2017
ms.assetid: 05d2321c-8acb-49d7-a6cd-8ef2220c6775
ms.openlocfilehash: fc1b75d7f2d97103f99b9dbf0fa8cbbfbe2270cd
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465060"
---
# <a name="using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting"></a>Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung
In diesem Thema wird das Format von Ablaufverfolgungsdaten und ihre Verwendung beschrieben. Dabei wird auch auf die Verwendung von Service Trace Viewer zur Problembehandlung in einer Anwendung eingegangen.  
  
## <a name="using-the-service-trace-viewer-tool"></a>Verwenden des Service Trace Viewer-Tools  
 Die Windows Communication Foundation (WCF) Service Trace Viewer-Tool können Sie die von WCF-Listenern finden Sie die Grundursache eines Fehlers erstellte diagnoseablaufverfolgungen zu korrelieren. Das Tool bietet Ihnen eine Möglichkeit, problemlos Gruppe anzeigen und Filtern von ablaufverfolgungen, damit Sie diagnostizieren, reparieren und überprüfen Sie Probleme mit WCF-Diensten. Weitere Informationen zur Verwendung dieses Tools finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).  
  
 Dieses Thema enthält Screenshots von ablaufverfolgungen, die durch die Ausführung generiert der [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel, bei der Anzeige mit den [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). In diesem Thema werden der Ablaufverfolgungsinhalt, Aktivitäten und ihre Korrelation erläutert. Zudem wird beschrieben, wie eine große Zahl von Ablaufverfolgungen im Rahmen der Problembehandlung analysiert werden können.  
  
## <a name="viewing-trace-content"></a>Anzeigen von Ablaufverfolgungsinhalt  
 Ein Ablaufverfolgungsereignis enthält die folgenden wichtigen Informationen:  
  
-   Aktivitätsname bei Festlegung  
  
-   Ausgabezeit  
  
-   Ablaufverfolgungsebene  
  
-   Name der Ablaufverfolgungsquelle  
  
-   Prozessname  
  
-   Thread-ID  
  
-   Einen eindeutigen ablaufverfolgungsbezeichner, d. h. eine URL, die auf ein Ziel in der Microsoft-Docs verweist, von denen Sie weitere Informationen im Zusammenhang mit der Ablaufverfolgung erhalten können.  
  
 Alle diese finden Sie in der oberen rechten Bereich im Service Trace Viewer oder in der **Basisinformationen** Abschnitt in der formatierten Ansicht des Bereichs unten rechts, wenn die Auswahl einer Ablaufverfolgung.  
  
> [!NOTE]
>  Wenn sich der Client und der Dienst auf demselben Computer befinden, können die Ablaufverfolgungen für beide Anwendungen eingesehen werden. Diese können mit der gefiltert werden die **Prozessnamen** Spalte.  
  
 Zudem bietet die formatierte Ansicht eine Beschreibung der Ablaufverfolgung sowie zusätzliche detaillierte Informationen, sofern diese verfügbar sind. Dazu gehören Ausnahmeart und -nachricht, Aufruflisten, Nachrichtenaktion, Felder Von/Zu und andere Ausnahmeinformationen.  
  
 Die XML-Ansicht enthält die folgenden nützlichen XML-Tags:  
  
-   `<SubType>` (Ablaufverfolgungsebene).  
  
-   `<TimeCreated>`.  
  
-   `<Source>` (Name der Ablaufverfolgungsquelle).  
  
-   `<Correlation>` (Aktivitäts-Id festgelegt, wenn die Ausgabe der Ablaufverfolgung).  
  
-   `<Execution>` (Prozess- und Thread-Id).  
  
-   `<Computer>`.  
  
-   `<ExtendedData>`, einschließlich `<Action>`, `<MessageID>` und `<ActivityId>` im Nachrichtenheader festgelegt wird, wenn eine Nachricht gesendet wird.  
  
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
 Wenn die `System.ServiceModel` Ablaufverfolgungsquelle mit festgelegt ist eine `switchValue` anders als Off und `ActivityTracing`, WCF erstellt, Aktivitäten und Übertragungen für WCF-Verarbeitung.  
  
 Eine Aktivität ist eine logische Verarbeitungseinheit, die alle verknüpften Ablaufverfolgungen zusammenfasst. So können Sie beispielsweise eine Aktivität für jede Anforderung definieren. Übertragungen stellen eine kausale Beziehung zwischen Aktivitäten innerhalb von Endpunkten her. Durch die Weitergabe der Aktivitäts-ID können Sie Aktivitäten über Endpunkte hinweg verknüpfen. Dies kann erreicht werden, indem `propagateActivity` = `true` in der Konfiguration an jedem Endpunkt. Aktivitäten, Übertragungen und Weitergabe ermöglichen es Ihnen, die Fehlerkorrelation durchzuführen. Auf diese Weise können Sie die Grundursache eines Fehlers schneller ermitteln.  
  
 Auf dem Client wird eine WCF-Aktivität für jeden Objektmodellaufruf (beispielsweise Open ChannelFactory, Add, Divide usw..) erstellt. Jeder der vorgangsaufrufe wird in einer Aktivität "Aktion verarbeiten" verarbeitet.  
  
 Im folgenden Screenshot aus extrahiert die [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel der linke Bereich zeigt die Liste der Aktivitäten, die im Clientprozess, sortiert nach Zeitpunkt der Erstellung erstellt. Es folgt eine chronologische Liste von Aktivitäten:  
  
-   Kanalfactory erstellt (ClientBase).  
  
-   Kanalfactory geöffnet.  
  
-   Add-Aktion (Hinzufügen) verarbeitet.  
  
-   Einrichtung der Sicherheitssitzung (in diesem besteht bei der ersten Anforderung) und verarbeiteten drei Sicherheitsinfrastruktur-Antwortnachrichten an: RST, RSTR, SCT (Process Message 1, 2, 3).  
  
-   Anforderungen Subtract, Multiply und Divide (Subtrahieren, Multiplizieren und Dividieren) verarbeitet.  
  
-   Kanalfactory geschlossen, dabei sichere Sitzung beendet und Sicherheitsantwort Cancel (Abbrechen) verarbeitet.  
  
 Die Sicherheitsinfrastrukturnachrichten sind aufgrund der Bindung wsHttpBinding sichtbar.  
  
> [!NOTE]
>  In WCF werden Antwortnachrichten, die zunächst in einer separaten Aktivität (Nachricht verarbeiten) verarbeitet werden, bevor wir sie mit der entsprechenden Processaction-Aktivität korreliert werden, die durch eine Übertragung die Anforderungsnachricht enthält. Das geschieht sowohl für Infrastrukturnachrichten als auch für asynchrone Anforderungen, da die Nachricht geprüft, der activityId-Header gelesen und die vorhandene ProcessAction-Aktivität mit der ID ermittelt werden muss, um die Korrelation vorzunehmen. Bei synchronen Anforderungen wird die Antwort blockiert, weshalb bekannt ist, mit welcher Verarbeitungsaktion die Antwort verknüpft ist.  
  
Die folgende Abbildung zeigt die WCF-Clientaktivitäten nach Erstellungszeit (linker Bereich) und ihre geschachtelten Aktivitäten und ablaufverfolgungen (oberer rechter Fensterbereich) aufgelistet:

 ![Screenshot der WCF-Client Aktivitäten, die nach erstellungsdauer aufgeführt.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-activities-creation-time.gif)  
  
 Wenn Sie im linken Bereich eine Aktivität auswählen, werden die verschachtelten Aktivitäten und Ablaufverfolgungen im rechten oberen Bereich angezeigt. Dabei handelt es sich somit um eine auf der Basis der ausgewählten übergeordneten Aktivität verkürzte hierarchische Ansicht der Aktivitätenliste auf der linken Seite. Da die ausgewählte Verarbeitungsaktion Add die erste Anforderung ist, enthält diese Aktivität die Aktivität Set Up Secure Session (Übertragung nach, Rückübertragung von) sowie Ablaufverfolgungen für die eigentliche Verarbeitung der Add-Aktion.  
  
 Wenn wir doppelklicken der Verarbeitungsaktion Add-Aktivität im linken Bereich klicken, sehen wir eine grafische Darstellung der WCF-Clientaktivitäten im Zusammenhang mit hinzufügen. Die erste Aktivität auf der linken Seite ist die Stammaktivität (0000), bei der es sich um die Standardaktivität handelt. WCF-überträgt aus der umgebungsaktivität heraus. Wenn dies nicht definiert ist, überträgt WCF aus 0000. Im vorliegenden Fall überträgt die zweite Aktivität, die Verarbeitungsaktion Add, aus 0 heraus. Dann wird Set Up Secure Session (Sichere Sitzung einrichten) angezeigt.  

 Die folgende Abbildung zeigt eine Diagrammansicht der WCF-Client-Aktivitäten, insbesondere Umgebungsaktivität (hier 0), Aktion verarbeiten und sichere Sitzung einrichten:   

 ![Ein Diagramm im Trace Viewer und Ambient-Aktivität und die Prozess-Aktion.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-activities-graph-ambient-process.gif)   
  
 Im oberen rechten Bereich sind alle Ablaufverfolgungen zu sehen, die mit der Process Action Add-Aktivität verknüpft sind. Das bedeutet, in ein und derselben Aktivität wurde die Anforderungsnachricht gesendet ("Sent a message over a channel", "Nachricht über einen Kanal gesendet") und die Antwort empfangen ("Received a message over a channel", "Nachricht über einen Kanal empfangen"). Dies wird im folgenden Diagramm dargestellt. Zur besseren Übersichtlichkeit ist die Set Up Secure Session-Aktivität im Diagramm reduziert.  
  
 Die folgende Abbildung zeigt eine Liste von ablaufverfolgungen für die Processaction-Aktivität. Wir senden die Anforderung und die Antwort zu empfangen, in der gleichen Aktivität.
 
 ![Screenshot des Trace Viewer zeigt eine Liste von ablaufverfolgungen für die Processaction-Aktivität](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/process-action-traces.gif)  
  
 Hier werden clientablaufverfolgungen zur besseren Verdeutlichung geladen, aber dienstablaufverfolgungen (empfangene Anforderungsnachrichten und gesendete Antwortnachricht) in der gleichen Aktivität angezeigt werden, wenn sie ebenfalls in das Tool geladen und `propagateActivity` wurde `true.` Dies wird in einer späteren Abbildung gezeigt.  
  
 Auf dem Dienst das Aktivitätsmodell die WCF-Konzepte folgendermaßen zugeordnet:  
  
1.  Ein ServiceHost wird erstellt und geöffnet (dadurch werden möglicherweise mehrere hostbezogene Aktivitäten erzeugt, z.&amp;#160;B. im Falle der Sicherheit).  
  
2.  Es wird eine Lauschaktivität für jeden Listener im ServiceHost erstellt (mit Übertragung in und aus Open ServiceHost).  
  
3.  Wenn der Listener eine kommunikationsanforderung, die vom Client initiierten erkannt wird, überträgt er zu einer "Receive Bytes"-Aktivität, die in der alle vom Client gesendeten Bytes verarbeitet werden. In dieser Aktivität sind alle Verbindungsfehler erkennbar, die während der Client-Dienst-Interaktion aufgetreten sind.  
  
4.  Für jede Gruppe von Bytes, die empfangen werden, die eine Nachricht entspricht, verarbeiten wir diese Bytes in einer Aktivität "Nachricht verarbeiten", in dem wir erstellen die WCF-Nachrichtenobjekt. In dieser Aktivität sind Fehler aufgrund eines ungültigen Umschlags oder einer falsch formatierten Nachricht erkennbar.  
  
5.  Sobald die Nachricht erstellt wird, erfolgt die Übertragung zu einer Process Action-Aktivität. Wenn `propagateActivity` sowohl für den Client als auch für den Dienst auf `true` festgelegt ist, verfügt diese Aktivität über dieselbe ID wie die auf dem Client definierte und zuvor beschriebene. Von dieser Phase beginnen wir, profitieren von der direkten Korrelation über Endpunkte hinweg, da alle ablaufverfolgungen in WCF ausgegeben, die der Anforderung verknüpft sind, in derselben Aktivität, einschließlich der Verarbeitung der Antwortnachricht sind.  
  
6.  Für die Out-of-Process-Aktion erstellen wir eine Aktivität "Execute User Code", um ablaufverfolgungen in Benutzercode von den angegebenen WCF ausgegeben ausgegebenen zu isolieren. Im vorherigen Beispiel wird die Ablaufverfolgung "Dienst sendet Add-Antwort" ggf. in der "Execute User Code"-Aktivität nicht in der vom Client weitergegebenen Aktivität ausgegeben.  
  
 In der nachfolgenden Abbildung ist die erste Aktivität auf der linken Seite die Stammaktivität (0000), bei der es sich um die Standardaktivität handelt. Die nächsten drei Aktivitäten dienen dazu, den ServiceHost zu öffnen. Die Aktivität in Spalte&amp;#160;5 ist der Listener, und die übrigen Aktivitäten (6 bis 8) beschreiben die WCF-Verarbeitung einer Nachricht, von der Byteverarbeitung bis zur Benutzercodeaktivierung.  

 Die folgende Abbildung zeigt eine Diagrammansicht der WCF-Dienstaktivitäten:   

 ![Screenshot des Trace Viewer zeigt eine Liste der WCF-Dienstaktivitäten](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-service-activities.gif)  
  
  
 Der folgende Screenshot zeigt die Aktivitäten sowohl des Clients als auch des Diensts. Die Process Action Add-Aktivität ist orange hervorgehoben. Pfeile verknüpfen die Anforderungs- und die Antwortnachrichten, die vom Client und vom Dienst gesendet und empfangen werden. Die ProcessAction-Ablaufverfolgungen sind über Prozesse im Diagramm verteilt, werden im oberen rechten Bereich jedoch als Teil derselben Aktivität angezeigt. In diesem Bereich sind Clientablaufverfolgungen für gesendete Nachrichten gefolgt von Dienstablaufverfolgungen für empfangene und verarbeitete Nachrichten zu sehen.  
  
 Die folgenden Abbildungen wird eine Diagrammansicht des beide WCF-Client und Dienst-Aktivitäten  
 
 ![Ein Diagramm von Trace Viewer, die beide WCF-Client und Dienst-Aktivitäten anzeigt.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-service-activities.gif)   
  
 Im folgenden Fehlerszenario werden Fehler- und Warnungsablaufverfolgungen im Dienst und auf dem Client verknüpft. Zunächst wird eine Ausnahme in Benutzercode für den Dienst ausgelöst (grüne Aktivität ganz rechts mit einer Warnungsablaufverfolgung für die Ausnahme "The service cannot process this request in user code", "Der Dienst kann diese Anforderung nicht in Benutzercode verarbeiten"). Beim Senden der Antwort an den Client wird erneut eine Warnungsablaufverfolgung ausgegeben, um die Fehlernachricht anzugeben (rosafarbene Aktivität links). Der Client schließt sodann seinen WCF-Client (gelbe Aktivität unten links), der die Verbindung zum Dienst abbricht. Der Dienst löst einen Fehler aus (längste rosafarbene Aktivität rechts).  
  
 ![Verwenden von Trace Viewer](../../../../../docs/framework/wcf/diagnostics/tracing/media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")  
Dienst- und clientübergreifende Fehlerkorrelation  
  
 Das Beispiel, das verwendet wird, um diese Ablaufverfolgungen zu generieren, ist eine Reihe von synchronen Anforderungen mit der Bindung wsHttpBinding. Abweichungen von diesem Diagramm treten bei Szenarien ohne Sicherheit oder bei asynchronen Anforderungen auf, bei denen die ProcessAction-Aktivität die Anfangs- und Endvorgänge umfasst, die den asynchronen Aufruf bilden, und Übertragungen zu einer Rückrufaktivität zeigt. Weitere Informationen über zusätzliche Szenarien finden Sie unter [End-To-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).  
  
## <a name="troubleshooting-using-the-service-trace-viewer"></a>Problembehandlung mit Service Trace Viewer  
 Wenn Sie Ablaufverfolgungsdateien in das Service Trace Viewer-Tool laden, können Sie jede beliebige rote oder gelbe Aktivität im linken Bereich auswählen, um die Ursache für ein Problem in Ihrer Anwendung zu ermitteln. Die Aktivität 000 verfügt i.&amp;#160;d.&amp;#160;R. über nicht behandelte Ausnahmen, mit denen sich der Benutzer befassen muss.  
  
  Die folgende Abbildung zeigt die zum Auswählen einer roten oder gelben Aktivität um die Ursache des Problems zu suchen.   
 ![Screenshot des roten oder gelben Aktivitäten für die Suche nach der Ursache des Problems.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/service-trace-viewer.gif)  
 
  
 Im oberen rechten Bereich können Sie Ablaufverfolgungen für die Aktivität prüfen, die Sie auf der linken Seite ausgewählt haben. Sie können dann rote oder gelbe Ablaufverfolgungen in diesem Bereich prüfen und sehen, wie sie korrelieren. Im vorangehenden Diagramm sind Warnungsablaufverfolgungen sowohl für den Client als auch für den Dienst in derselben Process Action-Aktivität erkennbar.  
  
 Wenn diese Ablaufverfolgungen nicht auf die Grundursache des Fehlers schließen lassen, können Sie auf die ausgewählte Aktivität im linken Bereich doppelklicken (hier Process Action). Das Diagramm mit den zugehörigen Aktivitäten wird dann angezeigt. Sie können die verknüpften Aktivitäten dann erweitern, (durch Klicken auf die Zeichen "+") um die erste ausgegebene Ablaufverfolgung in Rot oder Gelb in einer verknüpften Aktivität zu suchen. Erweitern Sie nach und nach die Aktivitäten, die direkt vor der betreffenden roten oder gelben Ablaufverfolgung ausgeführt wurden, und verfolgen Sie die Übertragungen zu verknüpften Aktivitäten oder Nachrichtenflüsse über Endpunkte hinweg, bis Sie die Grundursache des Problems gefunden haben.  
  
 ![Verwenden von Trace Viewer](../../../../../docs/framework/wcf/diagnostics/tracing/media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")  
Erweitern von Aktivitäten zur Ermittlung der Ursache eines Problems  
  
 Wenn die ServiceModel `ActivityTracing` deaktiviert, aber die ServiceModel-Ablaufverfolgung aktiviert ist, werden ServiceModel-Ablaufverfolgungen in der Aktivität 0000 ausgegeben. In diesem Fall ist es jedoch aufwändiger, die Korrelation dieser Ablaufverfolgungen zu verstehen.  
  
 Wenn die Nachrichtenprotokollierung aktiviert ist, können Sie auf der Registerkarte Nachricht nachsehen, welche Nachricht vom Fehler betroffen ist. Wenn Sie auf eine rote oder gelbe Nachricht doppelklicken, wird die Diagrammansicht der zugehörigen Aktivitäten angezeigt. Das sind die Aktivitäten, die am engsten mit der Anforderung verknüpft sind, bei der ein Fehler aufgetreten ist.  
  
 ![Screenshot des Trace Viewer mit aktivierter nachrichtenprotokollierung.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/message-logging-enabled.gif)  

Um mit der Problembehandlung beginnen, können Sie auch eine rote oder gelbe nachrichtenablaufverfolgung auswählen und doppelklicken, um die Grundursache zu ermitteln.  
  
## <a name="see-also"></a>Siehe auch
- [End-to-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
