---
title: Anzeigen von Nachrichtenprotokollen
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: c8313b14a45051b7828a1ab223a3da63b2e7a153
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291153"
---
# <a name="viewing-message-logs"></a>Anzeigen von Nachrichtenprotokollen

In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Anzeigen von Nachrichtenprotokollen im Service Trace Viewer  

 Eine Nachricht wird transformiert, wenn Sie von WCF verarbeitet wird. Deshalb spiegelt eine Nachricht, die protokolliert wird, lediglich den Nachrichteninhalt am Protokollierungspunkt wider, nicht den Inhalt der Verbindung.  
  
 Da die Ausgabe der Nachrichtenprotokollierung völlig unabhängig vom Übertragungsformat der Nachricht ist, gibt die Nachrichtenprotokollierung stets die decodierte Nachricht aus. Wenn Sie die Nachrichtenprotokollierung ordnungsgemäß konfiguriert haben, sollte jede protokollierte Nachricht als Klartext vorliegen. Beispielsweise wird das Format (Klartext) der protokollierten Nachrichten nicht durch die Verwendung eines binären Nachrichtenencoders beeinflusst.  
  
 Die Ausgabe von XmlWriterTraceListener ist eine Datei, die eine Sequenz von XML-Fragmenten enthält. Sie sollten beachten, dass die Datei keine gültige XML-Datei ist. Es wird empfohlen, das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zu verwenden, um die Nachrichtenprotokoll Dateien anzuzeigen. Weitere Informationen zur Verwendung dieses Tools finden [Sie unter Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.  
  
 In Service Trace Viewer werden Meldungen auf der Registerkarte **Nachricht** aufgeführt. Nachrichten, die einen Verarbeitungsfehler verursacht haben oder sich darauf beziehen, werden je nach Schweregrad des Fehlers gelb (Warnstufe) oder rot (Fehlerstufe) hervorgehoben. Wenn Sie auf die Nachricht doppelklicken, wird die Nachrichtenablaufverfolgung im Kontext der Verarbeitungsanforderung aufgerufen.  
  
> [!NOTE]
> Wenn eine Nachricht keinen Header aufweist, wird kein `<header/>`-Tag protokolliert.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Anzeigen von Nachrichten, die von einem Client, einem Relay und einem Dienst protokolliert werden  

 Ihre Umgebung kann einen Client enthalten, der eine Nachricht an ein Relay sendet, das die Nachricht wiederum an den Dienst weiterleitet. Wenn die Nachrichten Protokollierung an allen dreispeicher Orten aktiviert ist und alle drei Nachrichten Protokolle gleichzeitig im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden, wird der Austausch der Nachrichten Protokolle fälschlicherweise gerendert. Dies ist darauf zurückzuführen, dass `CorrelationId` und `ActivityId` im Nachrichtenheader nicht für jedes Absender-Empfängerpaar eindeutig sind.  
  
 Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen.  
  
- Zeigen Sie nur zwei der drei Nachrichten Protokolle im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zu einem beliebigen Zeitpunkt an.  
  
- Wenn Sie alle drei Protokolle gleichzeitig im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) anzeigen müssen, können Sie den Relaydienst ändern, indem Sie eine neue- <xref:System.ServiceModel.Channels.Message> Instanz erstellen. Bei dieser Instanz sollte es sich um eine Kopie des Textes der eingehenden Nachricht handeln und zusätzlich um alle Header mit Ausnahme des `ActivityId`-Headers und des `Action`-Headers. Der folgende Beispielcode veranschaulicht, wie Sie dabei vorgehen:  
  
```csharp
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a>Ausnahmefälle für ungenauen Nachrichtenprotokollierungsinhalt  

 Unter den folgenden Bedingungen entsprechen die protokollierten Nachrichten eventuell nicht genau der Darstellung des in der Verbindung vorhandenen octet-Streams.  
  
- Für BasicHttpBinding werden Umschlagheader für die eingehenden Nachrichten im /adressing/non-Namespace protokolliert.  
  
- Leerräume können nicht übereinstimmen.  
  
- Für eingehende Nachrichten können leere Elemente unterschiedlich dargestellt werden. Beispielsweise \<tag> \</tag> anstelle von\<tag/>  
  
- Wenn die bekannte PII-Protokollierung deaktiviert ist, indem standardmäßig oder ausdrücklich enableLoggingKnownPii auf "true" festgelegt wird.  
  
- Die Codierung wird für die Transformation in UTF-8 aktiviert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Nachrichtenprotokollierung](message-logging.md)
