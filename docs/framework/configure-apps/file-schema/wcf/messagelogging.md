---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: fd4d678b1e861a47762d8a64f85dcc052a30fe2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204800"
---
# \<messageLogging>

Dieses Element definiert die Einstellungen für die Nachrichtenprotokollierungsfunktionen von Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`logEntireMessage`|Ein boolescher Wert, der angibt, ob die ganze Nachricht (Nachrichtenheader und Text) protokolliert wird. Der Standard ist `false`, wobei nur der Nachrichtenheader protokolliert wird. Diese Einstellung beeinflusst alle Meldungsprotokollebenen (Dienst, Transport und fehlerhaft).|  
|`logMalformedMessages`|Ein boolescher Wert, der angibt, ob fehlerhafte Nachrichten protokolliert werden. Fehlerhafte Nachrichten werden bei `maxMessagesToLog` nicht berücksichtigt. Der Standardwert lautet `false`.|  
|`logMessagesAtServiceLevel`|Ein boolescher Wert, der angibt, ob Nachrichten auf Dienstebene (vor Verschlüsselung und transportbezogenen Transformationen) verfolgt werden. Der Standardwert lautet `false`.|  
|`logMessagesAtTransportLevel`|Ein boolescher Wert, der angibt, ob Nachrichten auf der Transportebene verfolgt werden. Alle in der Konfigurationsdatei angegebenen Filter werden angewendet, und nur Nachrichten, die den Filtern entsprechen, werden verfolgt. Der Standardwert lautet `false`.|  
|`maxMessagesToLog`|Eine positive ganze Zahl, die die maximale Anzahl an zu protokollierenden Nachrichten angibt. Der Standardwert lautet 1000.|  
|`maxSizeOfMessageToLog`|Eine positive ganze Zahl, die die maximale Größe einer zu protokollierenden Nachrichten in Bytes angibt. Nachrichten oberhalb dieses Grenzwerts werden nicht protokolliert. Diese Einstellung wirkt sich auf alle Nachverfolgungsebenen aus. Die Standardeinstellung ist 262144(0x4000).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Filter|Das `filters`-Element enthält eine Auflistung von XPath-Filtern. Wenn die Transportnachrichtenprotokollierung aktiviert ist (`logMessagesAtTransportLevel` ist `true`), werden nur Nachrichten protokolliert, die den Filtern entsprechen.<br /><br /> Filter werden nur auf Transportebene angewendet. Die Protokollierung von fehlerhaften Nachrichten und die Protokollierung von Nachrichten auf Dienstebene wird nicht von Filtern beeinflusst.<br /><br /> Das einzige Attribut für dieses Element (`filter`) ist ein XPath-Filter.<br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Diagnose|Definiert WCF-Einstellungen für die Laufzeitüberprüfung und Steuerungen für den Administrator.|  
  
## <a name="remarks"></a>Bemerkungen  

 Nachrichten werden auf drei verschiedenen Ebenen im Stapel protokolliert: Dienst, Transport und fehlerhaft. Jede Ebene kann separat aktiviert werden.  
  
 XPath-Filter können hinzugefügt werden, um bestimmte Nachrichten auf Transport- und Dienstebene zu protokollieren. Wenn keine Filter definiert werden, werden alle Meldungen protokolliert. Filter werden nur auf die Header der Nachricht angewendet. Der Nachrichtentext wird ignoriert. WCF ignoriert den Nachrichtentext, um die Leistung zu verbessern. Wenn Sie basierend auf dem Textinhalt filtern möchten, können Sie zu diesem Zweck einen benutzerdefinierten Listener mit einem Filter erstellen.  
  
 Sie müssen einen Ablaufverfolgungslistener erstellen, um die Nachrichtenablaufverfolgung zu aktivieren. Der Listener selbst kann jeder Listener sein, der mit der <xref:System.Diagnostics>-Ablaufverfolgungsarchitektur verwendet werden kann. Im folgenden Beispiel wird das Erstellen eines solchen Listeners veranschaulicht.  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a>Beispiel  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [Konfigurieren der Nachrichtenprotokollierung](../../../wcf/diagnostics/configuring-message-logging.md)
