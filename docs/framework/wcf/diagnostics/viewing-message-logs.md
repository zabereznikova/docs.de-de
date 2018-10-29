---
title: Anzeigen von Nachrichtenprotokollen
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: 5d007efc9667ee5380b69349d6a960554ab0d4fe
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199785"
---
# <a name="viewing-message-logs"></a>Anzeigen von Nachrichtenprotokollen
In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a>Anzeigen von Nachrichtenprotokollen im Service Trace Viewer  
 Eine Nachricht wird transformiert werden, während der Verarbeitung von WCF. Deshalb spiegelt eine Nachricht, die protokolliert wird, lediglich den Nachrichteninhalt am Protokollierungspunkt wider, nicht den Inhalt der Verbindung.  
  
 Da die Ausgabe der Nachrichtenprotokollierung völlig unabhängig vom Übertragungsformat der Nachricht ist, gibt die Nachrichtenprotokollierung stets die decodierte Nachricht aus. Wenn Sie die Nachrichtenprotokollierung ordnungsgemäß konfiguriert haben, sollte jede protokollierte Nachricht als Klartext vorliegen. Beispielsweise wird das Format (Klartext) der protokollierten Nachrichten nicht durch die Verwendung eines binären Nachrichtenencoders beeinflusst.  
  
 Die Ausgabe von XmlWriterTraceListener ist eine Datei, die eine Sequenz von XML-Fragmenten enthält. Sie sollten beachten, dass die Datei keine gültige XML-Datei ist. Es wird empfohlen, die Sie verwenden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) um die Nachrichtenprotokolldateien anzuzeigen. Weitere Informationen zur Verwendung dieses Tools finden Sie unter [mithilfe von Service Trace Viewer für korreliert Ablaufverfolgungen anzeigen und Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 In der Service Trace Viewer finden Sie Nachrichten in der **Nachricht** Registerkarte. Nachrichten, die einen Verarbeitungsfehler verursacht haben, werden je nach Schweregrad des Fehlers gelb (Warnstufe) oder rot (Fehlerstufe) dargestellt. Wenn Sie auf die Nachricht doppelklicken, wird die Nachrichtenablaufverfolgung im Kontext der Verarbeitungsanforderung aufgerufen.  
  
> [!NOTE]
>  Wenn eine Nachricht keinen Header aufweist, wird kein `<header/>`-Tag protokolliert.  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a>Anzeigen von Nachrichten, die von einem Client, einem Relay und einem Dienst protokolliert werden  
 Ihre Umgebung kann einen Client enthalten, der eine Nachricht an ein Relay sendet, das die Nachricht wiederum an den Dienst weiterleitet. Wenn die nachrichtenprotokollierung an allen drei Orten aktiviert ist, und alle drei Nachrichtenprotokolle werden angezeigt, [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) gleichzeitig der Nachrichtenprotokolle falsch wiedergegeben. Dies ist darauf zurückzuführen, dass `CorrelationId` und `ActivityId` im Nachrichtenheader nicht für jedes Absender-Empfängerpaar eindeutig sind.  
  
 Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen.  
  
-   Zeigen Sie nur zwei der drei Nachrichtenprotokolle im der [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zu einem beliebigen Zeitpunkt.  
  
-   Wenn Sie alle drei Protokolle anzeigen, müssen die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zur gleichen Zeit, können Sie den Relaydienst ändern, indem Sie beim Erstellen eines neuen <xref:System.ServiceModel.Channels.Message> Instanz. Bei dieser Instanz sollte es sich um eine Kopie des Textes der eingehenden Nachricht handeln und zusätzlich um alle Header mit Ausnahme des `ActivityId`-Headers und des `Action`-Headers. Der folgende Beispielcode veranschaulicht, wie Sie dabei vorgehen:  
  
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
  
-   Für BasicHttpBinding werden Umschlagheader für die eingehenden Nachrichten im /adressing/non-Namespace protokolliert.  
  
-   Leerräume können unpassend gepaart werden.  
  
-   Für eingehende Nachrichten können leere Elemente unterschiedlich dargestellt werden. Z. B. \<Tag >\</-Tag > anstelle von \<Tag / >  
  
-   Wenn die bekannte PII-Protokollierung deaktiviert ist, indem standardmäßig oder ausdrücklich enableLoggingKnownPii auf "true" festgelegt wird.  
  
-   Die Codierung wird für die Transformation in UTF-8 aktiviert.  
  
## <a name="see-also"></a>Siehe auch  
 [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)
