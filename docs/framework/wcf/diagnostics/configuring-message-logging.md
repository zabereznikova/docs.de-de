---
title: Konfigurieren der Nachrichtenprotokollierung
ms.date: 03/30/2017
helpviewer_keywords:
- message logging [WCF]
ms.assetid: 0ff4c857-8f09-4b85-9dc0-89084706e4c9
ms.openlocfilehash: 283f43239d6cf5aea5ea668397a52313ff526e2a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345183"
---
# <a name="configuring-message-logging"></a>Konfigurieren der Nachrichtenprotokollierung

In diesem Thema wird beschrieben, wie Sie die Nachrichtenprotokollierung für verschiedene Szenarien konfigurieren können.

## <a name="enabling-message-logging"></a>Aktivieren der Nachrichtenprotokollierung

Windows Communication Foundation (WCF) protokolliert Nachrichten standardmäßig nicht. Zum Aktivieren der Nachrichtenprotokollierung müssen Sie einen Ablaufverfolgungslistener zur `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle hinzufügen und in der Konfigurationsdatei Attribute für das `<messagelogging>`-Element festlegen.

Das folgende Beispiel zeigt, wie die Protokollierung aktiviert und zusätzliche Optionen angegeben werden.

```xml
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

Weitere Informationen zu den Einstellungen für die Nachrichtenprotokollierung finden Sie unter [Empfohlene Einstellungen für die Ablaufverfolgung und Nachrichtenprotokollierung](./tracing/recommended-settings-for-tracing-and-message-logging.md).

Mit `add` können Sie den Namen und den Typ des Listeners angeben, den Sie verwenden möchten. In der Beispielkonfiguration wird der Listener "messages" genannt, und der standardmäßige .NET Framework-Ablaufverfolgungslistener (`System.Diagnostics.XmlWriterTraceListener`) wird als zu verwendender Typ hinzugefügt. Wenn Sie `System.Diagnostics.XmlWriterTraceListener` verwenden, müssen Sie den Speicherort und den Namen der Ausgabedatei in der Konfigurationsdatei angeben. Legen Sie dafür `initializeData` auf den Namen der Protokolldatei fest. Andernfalls löst das System eine Ausnahme aus. Sie können auch einen benutzerdefinierten Listener implementieren, der Protokolle in einer Standarddatei ausgibt.

> [!NOTE]
> Da die Nachrichtenprotokollierung Speicherplatz verbraucht, beschränken Sie die Anzahl der Nachrichten, die auf die Festplatte geschrieben werden, auf einen bestimmten Dienst. Wenn die Nachrichtengrenze erreicht wird, wird eine Ablaufverfolgung auf Informationsebene erstellt und alle Nachrichtenprotokollierungsaktionen werden angehalten.

Die Protokollierungsebene sowie die zusätzlichen Optionen werden im Abschnitt Protokollieren von Ebenen und Optionen erläutert.

Das `switchValue`-Attribut von `source` ist nur für die Ablaufverfolgung gültig. Wenn Sie ein `switchValue`-Attribut für die `System.ServiceModel.MessageLogging`-Ablaufverfolgungsquelle wie folgt angeben, hat dies keine Auswirkungen.

```xml
<source name="System.ServiceModel.MessageLogging" switchValue="Verbose">
</source>
```

Wenn Sie die Ablaufverfolgungsquelle deaktivieren möchten, verwenden Sie stattdessen das `logMessagesAtServiceLevel`, `logMalformedMessages`-Attribut und das `logMessagesAtTransportLevel`-Attribut des `messageLogging`-Elements. Sie sollten all diese Attribute auf `false` festlegen. Dieser Schritt kann anhand der Konfigurationsdatei im vorigen Beispielcode über die Benutzeroberfläche des Configuration Editor oder über WMI durchgeführt werden. Weitere Informationen zum Configuration Editor-Tool finden Sie unter [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md). Weitere Informationen zu WMI finden Sie unter [Verwenden von Windows-Verwaltungsinstrumentation für Diagnose](./wmi/index.md).

## <a name="logging-levels-and-options"></a>Protokollieren von Ebenen und Optionen

Für eingehende Nachrichten erfolgt die Protokollierung direkt nach dem Erstellen der Nachricht, unmittelbar bevor die Nachricht Benutzercode auf der Dienstebene erhält und wenn falsch formatierte Nachrichten erkannt werden.

Für ausgehende Nachrichten erfolgt die Protokollierung unmittelbar nachdem die Nachricht den Benutzercode verlassen hat und unmittelbar bevor die Nachricht abgesendet wird.

WCF protokolliert Nachrichten auf zwei verschiedenen Ebenen, Dienst und Transport. Falsch formatierte Nachrichten werden auch protokolliert. Die drei Kategorien sind unabhängig voneinander und können in der Konfiguration getrennt aktiviert werden.

Sie können die Protokollierungsebene steuern, indem Sie das `logMessagesAtServiceLevel`, `logMalformedMessages`-Attribut und das `logMessagesAtTransportLevel`-Attribut des `messageLogging`-Elements festlegen.

### <a name="service-level"></a>Dienstebene

Auf dieser Ebene protokollierte Nachrichten sind im Begriff, (beim Empfangen) Benutzercode einzugeben oder (beim Senden) zu belassen. Wenn Filter definiert wurden, werden nur Nachrichten, die zu den Filtern passen, protokolliert. Andernfalls werden alle Nachrichten auf Dienstebene protokolliert. Auf dieser Ebene werden auch Infrastrukturnachrichten (Transaktionen, Peerkanal und Sicherheit) protokolliert, mit Ausnahme von mit zuverlässigem Messaging erstellten Nachrichten. Bei per Streaming übertragenen Nachrichten werden nur die Header protokolliert. Außerdem werden sichere Nachrichten auf dieser Ebene entschlüsselt protokolliert.

### <a name="transport-level"></a>Transportschicht

Auf dieser Ebene protokollierte Nachrichten können vor oder nach dem Transport codiert oder decodiert werden. Wenn Filter definiert wurden, werden nur Nachrichten, die zu den Filtern passen, protokolliert. Andernfalls werden alle Nachrichten auf der Transportschicht protokolliert. Auf dieser Ebene werden alle Infrastrukturnachrichten protokolliert, einschließlich zuverlässiger Messagingnachrichten. Bei per Streaming übertragenen Nachrichten werden nur die Header protokolliert. Außerdem werden sichere Nachrichten auf dieser Ebene verschlüsselt protokolliert, außer bei Verwendung eines sicheren Transports wie HTTPS.

### <a name="malformed-level"></a>Falsch formatierte Ebene

Falsch formatierte Nachrichten sind Nachrichten, die vom WCF-Stack in jeder Verarbeitungsphase abgelehnt werden. Falsch formatierte Nachrichten werden unverändert protokolliert: verschlüsselt, wenn sie bereits verschlüsselt sind, mit nicht ordnungsgemäßem XML usw. `maxSizeOfMessageToLog` definierte die zu protokollierende Nachrichtengröße als CDATA. Standardmäßig beträgt `maxSizeOfMessageToLog` 256K. Weitere Informationen zu diesem Attribut finden Sie im Abschnitt Andere Optionen.

### <a name="other-options"></a>Weitere Optionen

Zusätzlich zu den Protokollierungsebenen kann der Benutzer die folgenden Optionen angeben:

- Gesamte Nachricht protokollieren (`logEntireMessage`-Attribut): Dieser Wert gibt an, ob die ganze Meldung (Nachrichtenheader und Text) protokolliert wird. Der Standardwert lautet `false`, das bedeutet, dass nur der Nachrichtenheader protokolliert wird. Diese Einstellung beeinflusst die Nachrichtenprotokollierung auf Dienst- und Transportebene.

- Max. zu protokollierende Nachrichten (`maxMessagesToLog`-Attribut): Dieser Wert gibt die maximale Anzahl von zu protokollierenden Nachrichten an. Alle Nachrichten (Dienst, Transport und falsch formatierte Nachrichten) werden zu diesem Kontingent gezählt. Wenn das Kontingent erreicht wird, wird eine Ablaufverfolgung ausgegeben und keine weitere Nachricht protokolliert. Der Standardwert ist 10.000.

- Max. Größe der zu protokollierenden Nachrichten (`maxSizeOfMessageToLog`-Attribut): Dieser Wert gibt die maximale Größe einer zu protokollierenden Nachricht in Byte an. Nachrichten, die das Größenlimit überschreiten, werden nicht protokolliert, und für diese Nachricht werden keine weiteren Aktivitäten durchgeführt. Diese Einstellung wirkt sich auf alle Nachverfolgungsebenen aus. Wenn die ServiceModel-Ablaufverfolgung aktiviert ist, wird am ersten Protokollierungspunkt (ServiceModelSend* oder TransportReceive) zur Benachrichtigung des Benutzers eine Ablaufverfolgung auf Warnungsebene ausgegeben. Der Standardwert für Nachrichten auf Dienst- und auf Transportebene ist 256K, während der Standardwert für falsch formatierte Nachrichten 4K beträgt.

  > [!CAUTION]
  > Bei der Nachrichtengröße, die für den Vergleich mit `maxSizeOfMessageToLog` berechnet wird, handelt es sich um die Nachrichtengröße im Arbeitsspeicher vor der Serialisierung. Diese Größe kann von der tatsächlichen Länge der Nachrichtenzeichenfolge, die protokolliert wird, abweichen. In vielen Fällen überschreitet sie die tatsächliche Größe. Demzufolge werden Nachrichten möglicherweise nicht protokolliert. Um dieser Tatsache Rechnung zu tragen, können Sie das `maxSizeOfMessageToLog`-Attribut um 10 % größer angeben als die erwartete Nachrichtengröße. Wenn falsch formatierte Nachrichten protokolliert werden, kann die tatsächliche Festplattenspeichergröße, die von Nachrichtenprotokollen genutzt wird, die Größe des durch `maxSizeOfMessageToLog` angegebenen Werts um das Fünffache übersteigen.

Wenn in der Konfigurationsdatei kein Ablaufverfolgungslistener definiert ist, wird unabhängig von der angegebenen Protokollierungsebene keine Protokollierungsausgabe generiert.

Die Nachrichtenprotokollierungsoptionen, wie die in diesem Abschnitt beschriebenen Attribute, können zur Laufzeit mit der Windows-Verwaltungsinstrumentation (WMI) geändert werden. Dies kann durch den Zugriff auf die [AppDomainInfo-Instanz](./wmi/appdomaininfo.md) `LogMessagesAtServiceLevel`erfolgen, die die folgenden booleschen Eigenschaften verfügbar macht: , `LogMessagesAtTransportLevel`, und `LogMalformedMessages`. Wenn Sie einen Ablaufverfolgungslistener für die Nachrichtenprotokollierung konfigurieren, diese Optionen in der Konfiguration jedoch auf `false` festlegen, können Sie sie später, wenn die Anwendung ausgeführt wird, zu `true` ändern. Dadurch wird die Nachrichtenprotokollierung zur Laufzeit aktiviert. Entsprechend können Sie die Nachrichtenprotokollierung zur Laufzeit mit WMI deaktivieren, wenn Sie sie in der Konfigurationsdatei aktivieren. Weitere Informationen finden Sie unter [Verwenden von Windows-Verwaltungsinstrumentation für Diagnose](./wmi/index.md).

Das `source`-Feld in einem Nachrichtenprotokoll gibt an, in welchem Kontext die Nachricht protokolliert wird: beim Senden/Empfangen einer Anforderungsnachricht, für eine Anforderungsantwort oder eine unidirektionale Anforderung, auf der Dienstmodell- oder Transportschicht oder im Falle einer falsch formatierten Nachricht.

Bei falsch formatierten `source` Nachrichten `Malformed`ist gleich . Andernfalls verfügt die Quelle über die folgenden Werte auf der Grundlage des Kontexts.

Für Anforderung/Antwort

||Anforderung senden|Anforderung empfangen|Antwort senden|Antwort empfangen|
|-|------------------|---------------------|----------------|-------------------|
|Dienstmodellebene|Dienst<br /><br /> Ebene<br /><br /> Send<br /><br /> Anforderung|Dienst<br /><br /> Ebene<br /><br /> Empfangen<br /><br /> Anforderung|Dienst<br /><br /> Ebene<br /><br /> Send<br /><br /> Reply|Dienst<br /><br /> Ebene<br /><br /> Empfangen<br /><br /> Reply|
|Transportschicht|Transport<br /><br /> Send|Transport<br /><br /> Empfangen|Transport<br /><br /> Send|Transport<br /><br /> Empfangen|

Für unidirektionale Anforderung

||Anforderung senden|Anforderung empfangen|
|-|------------------|---------------------|
|Dienstmodellebene|Dienst<br /><br /> Ebene<br /><br /> Send<br /><br /> Datagramm|Dienst<br /><br /> Ebene<br /><br /> Empfangen<br /><br /> Datagramm|
|Transportschicht|Transport<br /><br /> Send|Transport<br /><br /> Empfangen|

## <a name="message-filters"></a>Nachrichtenfilter

Nachrichtenfilter werden im `messageLogging`-Konfigurationselement des `diagnostics`-Konfigurationsabschnitts definiert. Sie werden auf der Dienst- und Transportebene angewendet. Wenn mindestens ein Filter definiert ist, werden nur Nachrichten protokolliert, die mindestens einem der Filter entsprechen. Wenn kein Filter definiert wird, werden alle Meldungen protokolliert.

Filter unterstützen die gesamte Xpath-Syntax und werden in der Reihenfolge angewendet, in der sie in der Konfigurationsdatei angezeigt werden. Ein syntaktisch falscher Filter führt zu einer Konfigurationsausnahme.

Filter bieten unter Verwendung des `nodeQuota`-Attributs auch eine Sicherheitsfunktion, das die maximale Anzahl der Knoten im XPath DOM beschränkt, die im Hinblick auf den Filter geprüft werden.

Im Folgenden finden Sie ein Beispiel für das Konfigurieren eines Filters, der nur Nachrichten aufzeichnet, die über einen SOAP-Headerabschnitt verfügen.

```xml
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

Filter können nicht auf den Text einer Nachricht angewendet werden. Filter, die versuchen, den Text einer Nachricht zu bearbeiten, werden aus der Liste von Filtern entfernt. Außerdem wird ein entsprechendes Ereignis ausgegeben. Der folgende Filter würde z. B. aus der Filtertabelle entfernt werden.

```xml
<add xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">/s:Envelope/s:Body[contains(text(), "Hello")]</add>
```

## <a name="configuring-a-custom-listener"></a>Konfigurieren eines benutzerdefinierten Listeners

Sie können auch einen benutzerdefinierten Listener mit zusätzlichen Optionen konfigurieren. Ein benutzerdefinierter Listener kann nützlich sein, um vor der Protokollierung anwendungsspezifische PII-Elemente von Nachrichten zu filtern. Das folgende Beispiel veranschaulicht eine benutzerdefinierte Listenerkonfiguration.

```xml
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

Das `type`-Attribut sollte auf einen vollqualifizierten Assemblynamen festgelegt werden.

## <a name="see-also"></a>Siehe auch

- [\<MessageLogging>](../../configure-apps/file-schema/wcf/messagelogging.md)
- [Nachrichtenprotokollierung](message-logging.md)
- [Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung](./tracing/recommended-settings-for-tracing-and-message-logging.md)
