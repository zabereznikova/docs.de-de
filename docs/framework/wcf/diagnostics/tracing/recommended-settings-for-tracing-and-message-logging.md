---
title: "Empfohlene Einstellungen f&#252;r Ablaufverfolgung und Nachrichtenprotokollierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Empfohlene Einstellungen f&#252;r Ablaufverfolgung und Nachrichtenprotokollierung
In diesem Thema werden empfohlene Ablaufverfolgungs\- und Nachrichtenprotokollierungseinstellungen für andere Arbeitsumfelder beschrieben.  
  
## Empfohlene Einstellungen für eine Produktionsumgebung  
 Legen Sie in einer Produktionsumgebung, wenn Sie WCF\-Ablaufverfolgungsquellen verwenden, `switchValue` auf Warnung fest.  Legen Sie, wenn Sie die WCF `System.ServiceModel`\-Ablaufverfolgungsquelle verwenden, das `switchValue`\-Attribut auf `Warning` und das `propagateActivity`\-Attribut auf `true` fest.  Legen Sie, wenn Sie eine benutzerdefinierte Ablaufverfolgungsquelle verwenden, das `switchValue`\-Attribut auf `Warning, ActivityTracing` fest.  Verwenden Sie manuell dafür das [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  Wenn Sie keinen Treffer in der Leistung erwarten, können Sie das `switchValue`\-Attribut in allen zuvor erwähnten Fällen auf `Information` festlegen, wodurch relativ viele Ablaufverfolgungsdaten generiert werden.  Im folgenden Beispiel werden diese empfohlenen Einstellungen veranschaulicht.  
  
```  
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
  
## Empfohlene Einstellungen für Bereitstellung oder Debuggen  
 Wählen Sie in einer Bereitstellungs\- oder Debugumgebung `Information` oder `Verbose` zusammen mit `ActivityTracing` entweder für eine benutzerdefinierte oder `System.ServiceModel`\-Ablaufverfolgungsquelle.  Zum Optimieren des Debugvorgangs müssen Sie der Konfiguration auch eine zusätzliche Ablaufverfolgungsquelle \(`System.ServiceModel.MessageLogging`\) hinzufügen, um die Meldungsprotokollierung zu aktivieren.  Beachten Sie, dass das `switchValue`\-Attribut keine Auswirkungen auf diese Ablaufverfolgungsquelle hat.  
  
 Im folgenden Beispiel keyword werden die empfohlenen Einstellungen veranschaulicht und ein freigegebener Listener wird verwendet, der das `XmlWriterTraceListener` nutzt.  
  
```  
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
  
## Verwenden von WMI zum Ändern von Einstellungen  
 Mit WMI können Sie Konfigurationseinstellungen zur Laufzeit ändern \(durch Aktivieren des `wmiProviderEnabled`\-Attributs in der Konfiguration, wie im vorherigen Konfigurationsbeispiel dargestellt\).  Sie können beispielsweise mit WMI im CIM\-Studio zur Laufzeit die Ablaufverfolgungsquellenebenen von Warnung in Information ändern.  Beachten Sie dabei, dass die Leistungseinbußen von Livedebuggen auf diese Weise sehr hoch sein können.  Weitere Informationen zur Verwendung von WMI finden Sie unter [Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
## Aktivieren von korrelierenden Ereignissen in der ASP.NET\-Ablaufverfolgung  
 ASP.NET\-Ereignisse legen die Korrelation\-ID \(ActivityID\) nicht fest, außer wenn die Ablaufverfolgung von ASP.NET\-Ereignissen aktiviert wird.  Um die korrelierten Ereignisse korrekt zu erkennen, müssen Sie die Ablaufverfolgung von ASP.NET\-Ereignissen aktivieren, indem Sie den folgenden Befehl in der Befehlskonsole verwenden \(Sie starten die Befehlskonsole, indem Sie im Menü **Start** auf **Ausführen** klicken und dann **cmd** eingeben\):  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 Verwenden Sie den folgenden Befehl, um die Ablaufverfolgung von ASP.NET\-Ereignissen zu deaktivieren:  
  
```  
logman stop mytrace -ets  
```  
  
## Siehe auch  
 [Verwenden der Windows\-Verwaltungsinstrumentation für die Diagnose](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)