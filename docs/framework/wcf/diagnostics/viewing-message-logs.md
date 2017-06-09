---
title: "Anzeigen von Nachrichtenprotokollen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Anzeigen von Nachrichtenprotokollen
In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.  
  
## Anzeigen von Nachrichtenprotokollen im Service Trace Viewer  
 Eine Nachricht wird während ihrer Verarbeitung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] umgewandelt.Deshalb spiegelt eine Nachricht, die protokolliert wird, lediglich den Nachrichteninhalt am Protokollierungspunkt wider, nicht den Inhalt der Verbindung.  
  
 Da die Ausgabe der Nachrichtenprotokollierung völlig unabhängig vom Übertragungsformat der Nachricht ist, gibt die Nachrichtenprotokollierung stets die decodierte Nachricht aus.Wenn Sie die Nachrichtenprotokollierung ordnungsgemäß konfiguriert haben, sollte jede protokollierte Nachricht als Klartext vorliegen.Beispielsweise wird das Format \(Klartext\) der protokollierten Nachrichten nicht durch die Verwendung eines binären Nachrichtenencoders beeinflusst.  
  
 Die Ausgabe von XmlWriterTraceListener ist eine Datei, die eine Sequenz von XML\-Fragmenten enthält.Sie sollten beachten, dass die Datei keine gültige XML\-Datei ist.Es wird empfohlen, dass Sie das [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) verwenden, um die Nachrichtenprotokolldateien anzuzeigen.Weitere Informationen zur Verwendung dieses Tools finden Sie unter [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Im Service Trace Viewer werden Nachrichten auf der Registerkarte **Nachricht** aufgelistet.Nachrichten, die einen Verarbeitungsfehler verursacht haben, werden je nach Schweregrad des Fehlers gelb \(Warnstufe\) oder rot \(Fehlerstufe\) dargestellt.Wenn Sie auf die Nachricht doppelklicken, wird die Nachrichtenablaufverfolgung im Kontext der Verarbeitungsanforderung aufgerufen.  
  
> [!NOTE]
>  Wenn eine Nachricht keinen Header aufweist, wird kein `<header/>`\-Tag protokolliert.  
  
## Anzeigen von Nachrichten, die von einem Client, einem Relay und einem Dienst protokolliert werden  
 Ihre Umgebung kann einen Client enthalten, der eine Nachricht an ein Relay sendet, das die Nachricht wiederum an den Dienst weiterleitet.Wenn die Nachrichtenprotokollierung an allen drei Orten aktiviert wird und alle drei Nachrichtenprotokolle im [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) gleichzeitig angezeigt werden, wird der Austausch der Nachrichtenprotokolle falsch wiedergegeben.Dies ist darauf zurückzuführen, dass `CorrelationId` und `ActivityId` im Nachrichtenheader nicht für jedes Absender\-Empfängerpaar eindeutig sind.  
  
 Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen.  
  
-   Zeigen Sie jeweils nur zwei der drei Nachrichtenprotokolle im [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) an.  
  
-   Falls alle drei Protokolle gleichzeitig im [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden sollen, können Sie den Relaydienst ändern, indem Sie eine neue <xref:System.ServiceModel.Channels.Message>\-Instanz erstellen.Bei dieser Instanz sollte es sich um eine Kopie des Textes der eingehenden Nachricht handeln und zusätzlich um alle Header mit Ausnahme des `ActivityId`\-Headers und des `Action`\-Headers.Der folgende Beispielcode veranschaulicht, wie Sie dabei vorgehen:  
  
```  
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
  
## Ausnahmefälle für ungenauen Nachrichtenprotokollierungsinhalt  
 Unter den folgenden Bedingungen entsprechen die protokollierten Nachrichten eventuell nicht genau der Darstellung des in der Verbindung vorhandenen octet\-Streams.  
  
-   Für BasicHttpBinding werden Umschlagheader für die eingehenden Nachrichten im \/adressing\/non\-Namespace protokolliert.  
  
-   Leerräume können unpassend gepaart werden.  
  
-   Für eingehende Nachrichten können leere Elemente unterschiedlich dargestellt werden.Zum Beispiel \<tag\>\<\>\/tag\< statt \>tag\/  
  
-   Wenn die bekannte PII\-Protokollierung deaktiviert ist, indem standardmäßig oder ausdrücklich enableLoggingKnownPii auf "true" festgelegt wird.  
  
-   Die Codierung wird für die Umwandlung in UTF\-8 aktiviert.  
  
## Siehe auch  
 [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)   
 [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)