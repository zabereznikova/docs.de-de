---
title: "Konfigurieren der Nachrichtenprotokollierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Nachrichtenprotokollierung [WCF]"
ms.assetid: 0ff4c857-8f09-4b85-9dc0-89084706e4c9
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Konfigurieren der Nachrichtenprotokollierung
In diesem Thema wird beschrieben, wie Sie die Nachrichtenprotokollierung für verschiedene Szenarien konfigurieren können.  
  
## Aktivieren der Nachrichtenprotokollierung  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protokolliert standardmäßig keine Nachrichten.Zum Aktivieren der Nachrichtenprotokollierung müssen Sie einen Ablaufverfolgungslistener zur `System.ServiceModel.MessageLogging`\-Ablaufverfolgungsquelle hinzufügen und in der Konfigurationsdatei Attribute für das `<messagelogging>`\-Element festlegen.  
  
 Das folgende Beispiel zeigt, wie die Protokollierung aktiviert und zusätzliche Optionen angegeben werden.  
  
```  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
    </sources>  
</system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics>  
    <messageLogging   
         logEntireMessage="true"   
         logMalformedMessages="false"  
         logMessagesAtServiceLevel="true"   
         logMessagesAtTransportLevel="false"  
         maxMessagesToLog="3000"  
         maxSizeOfMessageToLog="2000"/>  
  </diagnostics>  
</system.serviceModel>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den Einstellungen für die Nachrichtenprotokollierung finden Sie unter [Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md).  
  
 Mit `add` können Sie den Namen und den Typ des Listeners angeben, den Sie verwenden möchten.In der Beispielkonfiguration wird der Listener "messages" genannt, und der standardmäßige .NET Framework\-Ablaufverfolgungslistener \(`System.Diagnostics.XmlWriterTraceListener`\) wird als zu verwendender Typ hinzugefügt.Wenn Sie `System.Diagnostics.XmlWriterTraceListener` verwenden, müssen Sie den Speicherort und den Namen der Ausgabedatei in der Konfigurationsdatei angeben.Legen Sie dafür `initializeData` auf den Namen der Protokolldatei fest.Andernfalls löst das System eine Ausnahme aus.Sie können auch einen benutzerdefinierten Listener implementieren, der Protokolle in einer Standarddatei ausgibt.  
  
> [!NOTE]
>  Da die Nachrichtenprotokollierung Speicherplatz verbraucht, beschränken Sie die Anzahl der Nachrichten, die auf die Festplatte geschrieben werden, auf einen bestimmten Dienst.Wenn die Nachrichtengrenze erreicht wird, wird eine Ablaufverfolgung auf Informationsebene erstellt und alle Nachrichtenprotokollierungsaktionen werden angehalten.  
  
 Die Protokollierungsebene sowie die zusätzlichen Optionen werden im Abschnitt Protokollieren von Ebenen und Optionen erläutert.  
  
 Das `switchValue`\-Attribut von `source` ist nur für die Ablaufverfolgung gültig.Wenn Sie ein `switchValue`\-Attribut für die `System.ServiceModel.MessageLogging`\-Ablaufverfolgungsquelle wie folgt angeben, hat dies keine Auswirkungen.  
  
```  
<source name="System.ServiceModel.MessageLogging" switchValue="Verbose">  
```  
  
 Wenn Sie die Ablaufverfolgungsquelle deaktivieren möchten, verwenden Sie stattdessen das `logMessagesAtServiceLevel`, `logMalformedMessages`\-Attribut und das `logMessagesAtTransportLevel`\-Attribut des `messageLogging`\-Elements.Sie sollten all diese Attribute auf `false` festlegen.Dieser Schritt kann anhand der Konfigurationsdatei im vorigen Beispielcode über die Benutzeroberfläche des Configuration Editor oder über WMI durchgeführt werden.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] über das Configuration Editor\-Tool finden Sie unter [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] WMI finden Sie unter [Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
## Protokollieren von Ebenen und Optionen  
 Für eingehende Nachrichten erfolgt die Protokollierung direkt nach dem Erstellen der Nachricht, unmittelbar bevor die Nachricht Benutzercode auf der Dienstebene erhält und wenn falsch formatierte Nachrichten erkannt werden.  
  
 Für ausgehende Nachrichten erfolgt die Protokollierung unmittelbar nachdem die Nachricht den Benutzercode verlassen hat und unmittelbar bevor die Nachricht abgesendet wird.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] protokolliert Nachrichten auf zwei verschiedenen Ebenen, Dienst und Transport.Falsch formatierte Nachrichten werden auch protokolliert.Die drei Kategorien sind unabhängig voneinander und können in der Konfiguration getrennt aktiviert werden.  
  
 Sie können die Protokollierungsebene steuern, indem Sie das `logMessagesAtServiceLevel`, `logMalformedMessages`\-Attribut und das `logMessagesAtTransportLevel`\-Attribut des `messageLogging`\-Elements festlegen.  
  
### Dienstebene  
 Auf dieser Ebene protokollierte Nachrichten sind im Begriff, \(beim Empfangen\) Benutzercode einzugeben oder \(beim Senden\) zu belassen.Wenn Filter definiert wurden, werden nur Nachrichten, die zu den Filtern passen, protokolliert.Andernfalls werden alle Nachrichten auf Dienstebene protokolliert.Auf dieser Ebene werden auch Infrastrukturnachrichten \(Transaktionen, Peerkanal und Sicherheit\) protokolliert, mit Ausnahme von mit zuverlässigem Messaging erstellten Nachrichten.Bei per Streaming übertragenen Nachrichten werden nur die Header protokolliert.Außerdem werden sichere Nachrichten auf dieser Ebene entschlüsselt protokolliert.  
  
### Transportschicht  
 Auf dieser Ebene protokollierte Nachrichten können vor oder nach dem Transport codiert oder decodiert werden.Wenn Filter definiert wurden, werden nur Nachrichten, die zu den Filtern passen, protokolliert.Andernfalls werden alle Nachrichten auf der Transportschicht protokolliert.Auf dieser Ebene werden alle Infrastrukturnachrichten protokolliert, einschließlich zuverlässiger Messagingnachrichten.Bei per Streaming übertragenen Nachrichten werden nur die Header protokolliert.Außerdem werden sichere Nachrichten auf dieser Ebene verschlüsselt protokolliert, außer bei Verwendung eines sicheren Transports wie HTTPS.  
  
### Falsch formatierte Ebene  
 Falsch formatierte Nachrichten sind Nachrichten, die vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Stapel in irgendeiner Phase der Verarbeitung abgelehnt werden.Falsch formatierte Nachrichten werden unverändert protokolliert: verschlüsselt, wenn sie bereits verschlüsselt sind, mit nicht ordnungsgemäßem XML usw.`maxSizeOfMessageToLog` definierte die zu protokollierende Nachrichtengröße als CDATA.Standardmäßig beträgt `maxSizeOfMessageToLog` 256K.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu diesem Attribut finden Sie im Abschnitt Weitere Optionen.  
  
### Weitere Optionen  
 Zusätzlich zu den Protokollierungsebenen kann der Benutzer die folgenden Optionen angeben:  
  
-   Gesamte Nachricht protokollieren \(`logEntireMessage`\-Attribut\): Dieser Wert gibt an, ob die ganze Meldung \(Nachrichtenheader und Text\) protokolliert wird.Der Standardwert lautet `false`, das bedeutet, dass nur der Nachrichtenheader protokolliert wird.Diese Einstellung beeinflusst die Nachrichtenprotokollierung auf Dienst\- und Transportebene.  
  
-   Max. zu protokollierende Nachrichten \(`maxMessagesToLog`\-Attribut\): Dieser Wert gibt die maximale Anzahl von zu protokollierenden Nachrichten an.Alle Nachrichten \(Dienst, Transport und falsch formatierte Nachrichten\) werden zu diesem Kontingent gezählt.Wenn das Kontingent erreicht wird, wird eine Ablaufverfolgung ausgegeben und keine weitere Nachricht protokolliert.Der Standardwert ist 10000.  
  
-   Max. Größe der zu protokollierenden Nachrichten \(`maxSizeOfMessageToLog`\-Attribut\): Dieser Wert gibt die maximale Größe einer zu protokollierenden Nachricht in Byte an.Nachrichten, die das Größenlimit überschreiten, werden nicht protokolliert, und für diese Nachricht werden keine weiteren Aktivitäten durchgeführt.Diese Einstellung wirkt sich auf alle Nachverfolgungsebenen aus.Wenn die ServiceModel\-Ablaufverfolgung aktiviert ist, wird am ersten Protokollierungspunkt \(ServiceModelSend\* oder TransportReceive\) zur Benachrichtigung des Benutzers eine Ablaufverfolgung auf Warnungsebene ausgegeben.Der Standardwert für Nachrichten auf Dienst\- und auf Transportebene ist 256K, während der Standardwert für falsch formatierte Nachrichten 4K beträgt.  
  
    > [!CAUTION]
    >  Bei der Nachrichtengröße, die für den Vergleich mit `maxSizeOfMessageToLog` berechnet wird, handelt es sich um die Nachrichtengröße im Arbeitsspeicher vor der Serialisierung.Diese Größe kann von der tatsächlichen Länge der Nachrichtenzeichenfolge, die protokolliert wird, abweichen. In vielen Fällen überschreitet sie die tatsächliche Größe.Demzufolge werden Nachrichten möglicherweise nicht protokolliert.Um dieser Tatsache Rechnung zu tragen, können Sie das `maxSizeOfMessageToLog`\-Attribut um 10 % größer angeben als die erwartete Nachrichtengröße.Wenn falsch formatierte Nachrichten protokolliert werden, kann die tatsächliche Festplattenspeichergröße, die von Nachrichtenprotokollen genutzt wird, die Größe des durch `maxSizeOfMessageToLog` angegebenen Werts um das Fünffache übersteigen.  
  
 Wenn in der Konfigurationsdatei kein Ablaufverfolgungslistener definiert ist, wird unabhängig von der angegebenen Protokollierungsebene keine Protokollierungsausgabe generiert.  
  
 Die Nachrichtenprotokollierungsoptionen, wie die in diesem Abschnitt beschriebenen Attribute, können zur Laufzeit mit der Windows\-Verwaltungsinstrumentation \(WMI\) geändert werden.Dies kann durch Zugreifen auf die [AppDomainInfo](../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)\-Instanz erfolgen, die folgende boolesche Eigenschaften verfügbar macht: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel` und `LogMalformedMessages`.Wenn Sie daher einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, in `true` ändern.Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert.Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
 Das `source`\-Feld in einem Nachrichtenprotokoll gibt an, in welchem Kontext die Nachricht protokolliert wird: beim Senden\/Empfangen einer Anforderungsnachricht, für eine Anforderungsantwort oder eine unidirektionale Anforderung, auf der Dienstmodell\- oder Transportschicht oder im Falle einer falsch formatierten Nachricht.  
  
 Bei falsch formatierten Nachrichten ist `source` mit `Malformed` identisch.Andernfalls verfügt die Quelle über die folgenden Werte auf der Grundlage des Kontexts.  
  
 Für Anforderung\/Antwort  
  
||Anforderung senden|Anforderung empfangen|Antwort senden|Antwort empfangen|  
|-|------------------------|---------------------------|--------------------|-----------------------|  
|Dienstmodellebene|Dienst<br /><br /> Ebene<br /><br /> Senden<br /><br /> Anforderung|Dienst<br /><br /> Ebene<br /><br /> Receive<br /><br /> Anforderung|Dienst<br /><br /> Ebene<br /><br /> Senden<br /><br /> Antworten|Dienst<br /><br /> Ebene<br /><br /> Receive<br /><br /> Antworten|  
|Transportschicht|Transport<br /><br /> Senden|Transport<br /><br /> Receive|Transport<br /><br /> Senden|Transport<br /><br /> Receive|  
  
 Für unidirektionale Anforderung  
  
||Anforderung senden|Anforderung empfangen|  
|-|------------------------|---------------------------|  
|Dienstmodellebene|Dienst<br /><br /> Ebene<br /><br /> Senden<br /><br /> Datagramm|Dienst<br /><br /> Ebene<br /><br /> Receive<br /><br /> Datagramm|  
|Transportschicht|Transport<br /><br /> Senden|Transport<br /><br /> Receive|  
  
## Nachrichtenfilter  
 Nachrichtenfilter werden im `messageLogging`\-Konfigurationselement des `diagnostics`\-Konfigurationsabschnitts definiert.Sie werden auf der Dienst\- und Transportebene angewendet.Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen.Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.  
  
 Filter unterstützen die gesamte Xpath\-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden.Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.  
  
 Filter bieten unter Verwendung des `nodeQuota`\-Attributs auch eine Sicherheitsfunktion, das die maximale Anzahl der Knoten im XPath DOM, die im Hinblick auf den Filter geprüft werden, beschränkt.  
  
 Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP\-Headerabschnitt verfügen.  
  
```  
<messageLogging logEntireMessage="true"  
    logMalformedMessages="true"   
    logMessagesAtServiceLevel="true"  
    logMessagesAtTransportLevel="true"  
    maxMessagesToLog="420">  
    <filters>  
        <add nodeQuota="10" xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                 /soap:Envelope/soap:Header  
        </add>  
     </filters>  
</messageLogging>  
```  
  
 Filter können nicht auf den Text einer Nachricht angewendet werden.Filter, die versuchen, den Text einer Nachricht zu bearbeiten, werden aus der Liste von Filtern entfernt.Außerdem wird ein entsprechendes Ereignis ausgegeben.Der folgende Filter würde z. B. aus der Filtertabelle entfernt werden.  
  
```  
<add xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">/s:Envelope/s:Body[contains(text(), "Hello")]</add>  
```  
  
## Konfigurieren eines benutzerdefinierten Listeners  
 Sie können auch einen benutzerdefinierten Listener mit zusätzlichen Optionen konfigurieren.Ein benutzerdefinierter Listener kann nützlich sein, um vor der Protokollierung anwendungsspezifische PII\-Elemente von Nachrichten zu filtern.Das folgende Beispiel veranschaulicht eine benutzerdefinierte Listenerkonfiguration.  
  
```  
<system.diagnostics>  
   <sources>  
     <source name="System.ServiceModel.MessageLogging">  
           <listeners>  
             <add name="MyListener"   
                    type="YourCustomListener"  
                    initializeData="c:\logs\messages.svclog"  
                    maxDiskSpace="1000"/>  
           </listeners>  
     </source>  
   </sources>  
</system.diagnostics>  
```  
  
 Das `type`\-Attribut sollte auf einen vollqualifizierten Assemblynamen festgelegt werden.  
  
## Siehe auch  
 [\<messageLogging\>](../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)   
 [Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/message-logging.md)   
 [Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)