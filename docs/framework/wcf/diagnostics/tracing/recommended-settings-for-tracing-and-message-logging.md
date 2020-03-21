---
title: Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 604aae2c0a0c5390428e7f1a2c99e17e90ee76a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185733"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a>Empfohlene Einstellungen für Ablaufverfolgung und Nachrichtenprotokollierung
In diesem Thema werden empfohlene Ablaufverfolgungs- und Nachrichtenprotokollierungseinstellungen für andere Arbeitsumfelder beschrieben.  
  
## <a name="recommended-settings-for-a-production-environment"></a>Empfohlene Einstellungen für eine Produktionsumgebung  
 Legen Sie in einer Produktionsumgebung, wenn Sie WCF-Ablaufverfolgungsquellen verwenden, `switchValue` auf Warnung fest. Legen Sie, wenn Sie die WCF `System.ServiceModel`-Ablaufverfolgungsquelle verwenden, das `switchValue`-Attribut auf `Warning` und das `propagateActivity`-Attribut auf `true` fest. Legen Sie, wenn Sie eine benutzerdefinierte Ablaufverfolgungsquelle verwenden, das `switchValue`-Attribut auf `Warning, ActivityTracing` fest. Dies kann manuell mit dem [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)erfolgen. Wenn Sie keinen Treffer in der Leistung erwarten, können Sie das `switchValue`-Attribut in allen zuvor erwähnten Fällen auf `Information` festlegen, wodurch relativ viele Ablaufverfolgungsdaten generiert werden. Im folgenden Beispiel werden diese empfohlenen Einstellungen veranschaulicht.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a>Empfohlene Einstellungen für Bereitstellung oder Debuggen  
 Wählen Sie in einer Bereitstellungs- oder Debugumgebung `Information` oder `Verbose` zusammen mit `ActivityTracing` entweder für eine benutzerdefinierte oder `System.ServiceModel`-Ablaufverfolgungsquelle. Zum Optimieren des Debugvorgangs müssen Sie der Konfiguration auch eine zusätzliche Ablaufverfolgungsquelle (`System.ServiceModel.MessageLogging`) hinzufügen, um die Meldungsprotokollierung zu aktivieren. Beachten Sie, dass das `switchValue`-Attribut keine Auswirkungen auf diese Ablaufverfolgungsquelle hat.  
  
 Im folgenden Beispiel keyword werden die empfohlenen Einstellungen veranschaulicht und ein freigegebener Listener wird verwendet, der das `XmlWriterTraceListener` nutzt.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a>Verwenden von WMI zum Ändern von Einstellungen  
 Mit WMI können Sie Konfigurationseinstellungen zur Laufzeit ändern (durch Aktivieren des `wmiProviderEnabled`-Attributs in der Konfiguration, wie im vorherigen Konfigurationsbeispiel dargestellt). Sie können beispielsweise mit WMI im CIM-Studio zur Laufzeit die Ablaufverfolgungsquellenebenen von Warnung in Information ändern. Beachten Sie dabei, dass die Leistungseinbußen von Livedebuggen auf diese Weise sehr hoch sein können. Weitere Informationen zur Verwendung von WMI finden Sie im Thema [Verwenden der Windows-Verwaltungsinstrumentation für Diesatos.](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a>Aktivieren von korrelierenden Ereignissen in der ASP.NET-Ablaufverfolgung  
 ASP.NET-Ereignisse legen die Korrelation-ID (ActivityID) nicht fest, außer wenn die Ablaufverfolgung von ASP.NET-Ereignissen aktiviert wird. Um korrelierte Ereignisse richtig anzuzeigen, müssen Sie ASP.NET Ereignisablaufverfolgung mit dem folgenden Befehl in der Befehlskonsole aktivieren, der aufgerufen werden kann, indem Sie zu **Starten**, **Ausführen** und geben Sie **cmd**,  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 Verwenden Sie den folgenden Befehl, um die Ablaufverfolgung von ASP.NET-Ereignissen zu deaktivieren:  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden der Windows-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
