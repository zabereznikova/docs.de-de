---
title: "Workflow&#252;berwachung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Workflow&#252;berwachung
Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework\-Ablaufverfolgungslistenern zu erfassen.Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist.Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows.Sie können sie mit der Ereignisablaufverfolgung \(ETW\) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.  
  
## Aktivieren der Debugablaufverfolgung in ETW  
 Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:  
  
1.  Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.  
  
2.  Wählen Sie in der Strukturansicht **Ereignisanzeige\-\>Anwendungs\- und Dienstprotokolle\-\>Microsoft\-\>Windows\-\>Anwendungsserver\-Anwendungen**.Klicken Sie mit der rechten Maustaste auf **Anwendungsserver\-Anwendungen**, und wählen Sie **Ansicht\>Analytische und Debugprotokolle einblenden** aus.Klicken Sie mit der rechten Maustaste auf **Debuggen**, und wählen Sie **Protokoll aktivieren**.  
  
3.  Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen.Wählen Sie **Ereignisanzeige\-\>Anwendungs\- und Dienstprotokolle\-\>Microsoft\-\>Windows\-\>Anwendungsserver\-Anwendungen**.Klicken Sie mit der rechten Maustaste auf **Debuggen**, und wählen Sie **Aktualisieren**.  
  
4.  Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes \(KB\). Es wird empfohlen, die Größe auf 32 KB zu erweitern.Gehen Sie hierzu folgendermaßen vor.  
  
    1.  Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis \(z. B. C:\\Windows\\Microsoft.NET\\Framework\\v4.0.21203\) aus: `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  Ändern Sie den \<bufferSize\>\-Wert in der Datei "Windows.ApplicationServer.Applications.man" in 32.  
  
        ```  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
  
        ```  
  
    3.  Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis \(z. B. C:\\Windows\\Microsoft.NET\\Framework\\v4.0.21203\) aus: `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  Wenn Sie .NET Framework 4 Client Profile verwenden, müssen Sie zuerst das ETW\-Manifest registrieren, indem Sie im .NET Framework 4\-Verzeichnis den folgenden Befehl ausführen: `ServiceModelReg.exe –i –c:etw`  
  
## Aktivieren der Debugablaufverfolgung mit System.Diagnostics  
 Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt.In diesem Beispiel wird ein [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) konfiguriert, um Ablaufverfolgungsinformationen in der Datei MyTraceLog.txt im aktuellen Verzeichnis zu speichern.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## Siehe auch  
 [Überwachung mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)